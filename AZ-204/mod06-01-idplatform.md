
# Microsoft IDプラットフォーム

[ドキュメント](https://docs.microsoft.com/ja-jp/azure/active-directory/develop/v2-overview)


# アカウントの種類

|アプリの種類|対象ユーザー|テナントの種類|
|-|-|-|
|基幹業務アプリ(LOB)|組織内のユーザー|シングルテナント|
|ISVが提供するアプリ|任意の組織のユーザー|マルチテナント|
|B2Cアプリ|消費者|B2C|

[ISV](https://ja.wikipedia.org/wiki/ISV) - パッケージソフトウェアの開発・販売会社の総称。サードパーティ。[コンピュータ製品やオペレーティングシステム（OS）、クラウドサービスなど基盤的なシステム製品の開発・販売・提供元にとって、自社製品に対応したソフトウェアを開発・販売している自社グループ外の企業のこと](http://e-words.jp/w/ISV.html)。独立系ソフトウェアベンダ。


# サインイン機能の提供 - Microsoft ID プラットフォーム

[Microsoft ID プラットフォーム](https://docs.microsoft.com/ja-jp/azure/active-directory/develop/v2-overview)により、開発者は、ユーザーや顧客が各自の Microsoft ID やソーシャル アカウントを使用してサインインできるアプリケーションを構築できます。

開発者は、機能を自分で実装することなしに、パスワードレス認証、ステップアップ認証、条件付きアクセスなど、ID およびセキュリティ領域における最新の革新的技術を統合できます。

Microsoft ID プラットフォームには、[MSAL](mod06-02-msal.md)が含まれます。


# 参考：Red Hat社による、セキュリティーの概念の解説

https://access.redhat.com/documentation/ja-jp/red_hat_jboss_enterprise_application_platform/7.1/html/security_architecture/overview_of_general_security_concepts


クレームベースのアイデンティティーシステムでは、システムはアイデンティティー情報を渡すことができますが、その情報をクレームと発行者 (またはオーソリティー) の 2 つに抽象化します。クレームは、ユーザー、グループ、アプリケーション、組織などの 1 つのサブジェクトが他のサブジェクトに関して作成するステートメントです。1 つまたは複数のクレームは、1 つまたは複数のトークンにパッケージ化され、プロバイダーによって発行されます。

# WS-Federation

https://techinfoofmicrosofttech.osscons.jp/index.php?WS-Federation

IBM、Microsoft、Novellの各社によって開発されたクレームベース認証の仕様。
主にエンプラ系で使用されるが、こちらはWS-Federationよりも、SAMLが主流になっている。



# セキュリティトークン

https://docs.microsoft.com/ja-jp/azure/active-directory/develop/security-tokens

- アクセストークン
- IDトークン

# 同意のフレームワーク

https://docs.microsoft.com/ja-jp/azure/active-directory/develop/consent-framework

https://jpazureid.github.io/blog/azure-active-directory/azure-ad-consent-framework/

# クレーム

https://www.atmarkit.co.jp/fdotnet/arcjournal/arcjournal16_06/arcjournal16_06_02.html

クレームとは、認証対象となるエンティティ（“サブジェクト”）に関する事実で、認証を行う別のエンティティ（“オーソリティ”）によって言及されます。

　クレームは、サブジェクトの任意の側面を表していればなんでもよく、実在する人物でも抽象的なリソースでもかまいません。クレームの典型的な例としては、“ボブは 21 歳を過ぎている”、“ボブは Contoso.com ドメインのリモート デバッガー グループに属している”、“ボブはスター アライアンス加盟航空会社のシルバー エリート メンバーである”などが挙げられます。クレームはオーソリティによって承認されます。

# 信頼

https://www.atmarkit.co.jp/fdotnet/arcjournal/arcjournal16_06/arcjournal16_06_02.html


エンティティ A がエンティティ B の発行したクレームは真実であると判断した場合に、“A は B を信頼している”と見なされます。

サブジェクトに関する B の言明を信頼することで、A はそのクレームを直接検証する手間を省くことができます。なお、このような場合も、エンティティ A は、クレームが実際に B により発行されたものであって偽造ではないという点については、確認を行う必要があります。

# JWT (Json Web Token)

https://tools.ietf.org/html/rfc7519

# eyJ

[jwt.ms](https://jwt.ms/#id_token=eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIng1dCI6IjdfWnVmMXR2a3dMeFlhSFMzcTZsVWpVWUlHdyIsImtpZCI6IjdfWnVmMXR2a3dMeFlhSFMzcTZsVWpVWUlHdyJ9.eyJhdWQiOiJiMTRhNzUwNS05NmU5LTQ5MjctOTFlOC0wNjAxZDBmYzljYWEiLCJpc3MiOiJodHRwczovL3N0cy53aW5kb3dzLm5ldC9mYTE1ZDY5Mi1lOWM3LTQ0NjAtYTc0My0yOWYyOTU2ZmQ0MjkvIiwiaWF0IjoxNTM2Mjc1MTI0LCJuYmYiOjE1MzYyNzUxMjQsImV4cCI6MTUzNjI3OTAyNCwiYWlvIjoiQVhRQWkvOElBQUFBcXhzdUIrUjREMnJGUXFPRVRPNFlkWGJMRDlrWjh4ZlhhZGVBTTBRMk5rTlQ1aXpmZzN1d2JXU1hodVNTajZVVDVoeTJENldxQXBCNWpLQTZaZ1o5ay9TVTI3dVY5Y2V0WGZMT3RwTnR0Z2s1RGNCdGsrTExzdHovSmcrZ1lSbXY5YlVVNFhscGhUYzZDODZKbWoxRkN3PT0iLCJhbXIiOlsicnNhIl0sImVtYWlsIjoiYWJlbGlAbWljcm9zb2Z0LmNvbSIsImZhbWlseV9uYW1lIjoiTGluY29sbiIsImdpdmVuX25hbWUiOiJBYmUiLCJpZHAiOiJodHRwczovL3N0cy53aW5kb3dzLm5ldC83MmY5ODhiZi04NmYxLTQxYWYtOTFhYi0yZDdjZDAxMWRiNDcvIiwiaXBhZGRyIjoiMTMxLjEwNy4yMjIuMjIiLCJuYW1lIjoiYWJlbGkiLCJub25jZSI6IjEyMzUyMyIsIm9pZCI6IjA1ODMzYjZiLWFhMWQtNDJkNC05ZWMwLTFiMmJiOTE5NDQzOCIsInJoIjoiSSIsInN1YiI6IjVfSjlyU3NzOC1qdnRfSWN1NnVlUk5MOHhYYjhMRjRGc2dfS29vQzJSSlEiLCJ0aWQiOiJmYTE1ZDY5Mi1lOWM3LTQ0NjAtYTc0My0yOWYyOTU2ZmQ0MjkiLCJ1bmlxdWVfbmFtZSI6IkFiZUxpQG1pY3Jvc29mdC5jb20iLCJ1dGkiOiJMeGVfNDZHcVRrT3BHU2ZUbG40RUFBIiwidmVyIjoiMS4wIn0=.UJQrCA6qn2bXq57qzGX_-D3HcPHqBMOKDPx4su1yKRLNErVD8xkxJLNLVRdASHqEcpyDctbdHccu6DPpkq5f0ibcaQFhejQNcABidJCTz0Bb2AbdUCTqAzdt9pdgQvMBnVH1xk3SCM6d4BbT4BkLLj10ZLasX7vRknaSjE_C5DI7Fg4WrZPwOhII1dB0HEZ_qpNaYXEiy-o94UJ94zCr07GgrqMsfYQqFR7kn-mn68AjvLcgwSfZvyR_yIK75S_K37vC3QryQ7cNoafDe9upql_6pB2ybMVlgWPs_DmbJ8g0om-sPlwyn74Cc1tW3ze-Xptw_2uVdPgWyqfuWAfq6Q)

で表示できる。


# aud

対象者。オーディエンス。 b14a7505-96e9-4927-91e8-0601d0fc9caa のような文字列である場合がある。

https://docs.microsoft.com/ja-jp/azure/active-directory/develop/id-tokens

文字列、アプリケーション ID URI	トークンの受信者を示します。 id_tokensでは、対象の受信者は Azure portal でアプリに割り当てられたアプリのアプリケーション ID です。 アプリでは、この値を検証し、値が一致しない場合はトークンを拒否する必要があります。



https://kamichidu.github.io/post/2017/01/24-about-json-web-token/

“aud” (Audience) (Optional)

JWTの想定利用者を意味します。 値として文字列かURI、またはそれらの配列を取ることができます。 値は大文字/小文字が区別されます。

発行する側はJWTの発行要求をしてきた相手を識別する文字列やURIを入れ込み、 発行された側はAudience Claimが存在する場合は自分向けに発行されたJWTなのかどうかを検証することに用います。

# AADへのアプリの登録


https://docs.microsoft.com/ja-jp/azure/active-directory/develop/app-objects-and-service-principals

ID とアクセスの管理機能を Azure AD に委任するには、アプリケーションを Azure AD のテナントに登録する必要があります。 アプリケーションを Azure AD に登録するときに、アプリケーションの ID 構成を作成します。これによって Azure AD との連携が可能となります。 

Azure portal でアプリを登録するときに、それがシングル テナント (自分のテナント内でのみアクセス可能) かマルチテナント (他のテナント内でアクセス可能) かを選択し、必要に応じてリダイレクト URI (アクセス トークンの送信先) を設定します。

アプリの登録が完了すると、ホーム テナントまたはディレクトリ内に存在するアプリ (アプリケーション オブジェクト) のグローバルに一意なインスタンスが作成されます。 また、アプリにグローバルに一意な ID (アプリまたはクライアント ID) も割り当てられます。

# アプリケーションオブジェクト

https://docs.microsoft.com/ja-jp/azure/active-directory/develop/app-objects-and-service-principals#application-object

Azure AD アプリケーションは、その唯一のアプリケーション オブジェクトによって定義されます。アプリケーション オブジェクトは、アプリケーションの登録先である Azure AD テナント (アプリケーションの "ホーム" テナントと呼ばれます) 内にあります。 

アプリケーション オブジェクトは、1 つ以上のサービス プリンシパル オブジェクトを作成するためのテンプレートまたはブループリントとして使用されます。 

サービス プリンシパルは、アプリケーションが使用されるすべてのテナントに作成されます。 

オブジェクト指向プログラミングのクラスと同様に、アプリケーション オブジェクトには、作成されたすべてのサービス プリンシパル (またはアプリケーション インスタンス) に適用されるいくつかの静的プロパティがあります。

# サービスプリンシパル オブジェクト

https://docs.microsoft.com/ja-jp/azure/active-directory/develop/app-objects-and-service-principals#service-principal-object

Azure AD テナントによってセキュリティ保護されているリソースにアクセスするためには、アクセスを必要とするエンティティをセキュリティ プリンシパルで表す必要があります。

この要件は、ユーザー (ユーザー プリンシパル) とアプリケーション (サービス プリンシパル) の両方に当てはまります。

サービス プリンシパルは、単一のテナントまたはディレクトリ内のグローバル アプリケーション オブジェクトのローカル表現、つまりアプリケーション インスタンスです。 

サービス プリンシパル オブジェクトには、特定のテナント内でアプリが実際に実行できること、アプリにアクセスできるユーザー、アプリからアクセスできるリソースを定義します。

アプリケーションが (登録または同意によって) テナント内のリソースへのアクセス許可を与えられると、サービス プリンシパル オブジェクトが作成されます。

ポータルの [エンタープライズ アプリケーション] ブレードは、テナントのサービス プリンシパルを一覧表示および管理するために使用されます。 

[Azure CLI 2.0 でサービスプリンシパルが簡単に作れる](https://blog.shibayan.jp/entry/20170123/1485154436)


# MSAL.js

MSAL.js は、シングルページ アプリケーションをサポートする唯一の Microsoft 認証ライブラリです。

1.0と2.0

※MSAL.jsは、[MSALが提供する多数のライブラリ](https://docs.microsoft.com/ja-jp/azure/active-directory/develop/msal-overview#languages-and-frameworks)の中の一種。MSAL.NET, MSAL Java, MSAL Python, MSAL for Android, MSAL for iOS, MSAL for macOSなど。

# 認証コード

MSAL.js 1.3 以前を使用するアプリケーションでは、承認コード フローはサポートされていません。

MSAL.js 2.0 以降では、ブラウザーのサード パーティ Cookie の制限に対応して、PKCE および CORS を使用した承認コード フローをサポートしています。 

暗黙的な許可フローは、MSAL.js 2.0 以降ではサポートされていません。

# 使い分け

SPA - [暗黙的な許可フロー](https://docs.microsoft.com/ja-jp/azure/active-directory/develop/v2-oauth2-implicit-grant-flow)

サーバーベースWebアプリ - [認証コード](https://docs.microsoft.com/ja-jp/azure/active-directory/develop/v2-oauth2-auth-code-flow)  

