# <a name="how-to-run-the-completed-project"></a><span data-ttu-id="71668-101">完了したプロジェクトを実行する方法</span><span class="sxs-lookup"><span data-stu-id="71668-101">How to run the completed project</span></span>

## <a name="prerequisites"></a><span data-ttu-id="71668-102">前提条件</span><span class="sxs-lookup"><span data-stu-id="71668-102">Prerequisites</span></span>

<span data-ttu-id="71668-103">このフォルダーで完了したプロジェクトを実行するには、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="71668-103">To run the completed project in this folder, you need the following:</span></span>

- <span data-ttu-id="71668-104">開発用コンピューターにインストールされている[.Net コア SDK](https://dotnet.microsoft.com/download) 。</span><span class="sxs-lookup"><span data-stu-id="71668-104">The [.NET Core SDK](https://dotnet.microsoft.com/download) installed on your development machine.</span></span> <span data-ttu-id="71668-105">(**注:** このチュートリアルは、.NET Core SDK バージョン2.2.401 を使用して作成されています。</span><span class="sxs-lookup"><span data-stu-id="71668-105">(**Note:** This tutorial was written with .NET Core SDK version 2.2.401.</span></span> <span data-ttu-id="71668-106">このガイドの手順は、他のバージョンでは動作しますが、テストされていません。)</span><span class="sxs-lookup"><span data-stu-id="71668-106">The steps in this guide may work with other versions, but that has not been tested.)</span></span>
- <span data-ttu-id="71668-107">Microsoft 職場または学校のアカウント。</span><span class="sxs-lookup"><span data-stu-id="71668-107">A Microsoft work or school account.</span></span>

<span data-ttu-id="71668-108">Microsoft アカウントを持っていない場合は、 [office 365 開発者プログラムにサインアップ](https://developer.microsoft.com/office/dev-program)して、無料の office 365 サブスクリプションを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="71668-108">If you don't have a Microsoft account, you can [sign up for the Office 365 Developer Program](https://developer.microsoft.com/office/dev-program) to get a free Office 365 subscription.</span></span>

## <a name="register-a-web-application-with-the-azure-active-directory-admin-center"></a><span data-ttu-id="71668-109">Web アプリケーションを Azure Active Directory 管理センターに登録する</span><span class="sxs-lookup"><span data-stu-id="71668-109">Register a web application with the Azure Active Directory admin center</span></span>

1. <span data-ttu-id="71668-110">ブラウザーを開き、[Azure Active Directory 管理センター](https://aad.portal.azure.com)へ移動して、**個人用アカウント** (別名: Microsoft アカウント)、または**職場/学校アカウント**を使用してログインします。</span><span class="sxs-lookup"><span data-stu-id="71668-110">Open a browser and navigate to the [Azure Active Directory admin center](https://aad.portal.azure.com) and login using a **personal account** (aka: Microsoft Account) or **Work or School Account**.</span></span>

1. <span data-ttu-id="71668-111">左側のナビゲーションで [ **Azure Active Directory** ] を選択し、[**管理**] の下にある [**アプリの登録**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="71668-111">Select **Azure Active Directory** in the left-hand navigation, then select **App registrations** under **Manage**.</span></span>

    ![<span data-ttu-id="71668-112">アプリの登録のスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="71668-112">A screenshot of the App registrations</span></span> ](/tutorial/images/aad-portal-app-registrations.png)

1. <span data-ttu-id="71668-113">**[新規登録]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="71668-113">Select **New registration**.</span></span> <span data-ttu-id="71668-114">**[アプリケーションを登録]** ページで、次のように値を設定します。</span><span class="sxs-lookup"><span data-stu-id="71668-114">On the **Register an application** page, set the values as follows.</span></span>

    - <span data-ttu-id="71668-115">`.NET Core Graph Tutorial` に **[名前]** を設定します。</span><span class="sxs-lookup"><span data-stu-id="71668-115">Set **Name** to `.NET Core Graph Tutorial`.</span></span>
    - <span data-ttu-id="71668-116">**サポートされているアカウントの種類**を**任意の組織ディレクトリのアカウント**に設定します。</span><span class="sxs-lookup"><span data-stu-id="71668-116">Set **Supported account types** to **Accounts in any organizational directory**.</span></span>
    - <span data-ttu-id="71668-117">**[リダイレクト URI]** を空のままにします。</span><span class="sxs-lookup"><span data-stu-id="71668-117">Leave **Redirect URI** empty.</span></span>

    ![[アプリケーションの登録] ページのスクリーンショット](/tutorial/images/aad-register-an-app.png)

1. <span data-ttu-id="71668-119">[**登録**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="71668-119">Select **Register**.</span></span> <span data-ttu-id="71668-120">**.Net コアグラフのチュートリアル**ページで、**アプリケーション (クライアント) ID**の値をコピーして保存し、次の手順で必要になります。</span><span class="sxs-lookup"><span data-stu-id="71668-120">On the **.NET Core Graph Tutorial** page, copy the value of the **Application (client) ID** and save it, you will need it in the next step.</span></span>

    ![新しいアプリの登録のアプリケーション ID のスクリーンショット](/tutorial/images/aad-application-id.png)

1. <span data-ttu-id="71668-122">[**リダイレクト URI を追加する**] リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="71668-122">Select the **Add a Redirect URI** link.</span></span> <span data-ttu-id="71668-123">[**リダイレクト uri** ] ページで、[**パブリッククライアント (モバイル、デスクトップ)] セクションの推奨されるリダイレクト uri**を見つけます。</span><span class="sxs-lookup"><span data-stu-id="71668-123">On the **Redirect URIs** page, locate the **Suggested Redirect URIs for public clients (mobile, desktop)** section.</span></span> <span data-ttu-id="71668-124">`https://login.microsoftonline.com/common/oauth2/nativeclient` URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="71668-124">Select the `https://login.microsoftonline.com/common/oauth2/nativeclient` URI.</span></span>

    ![リダイレクト Uri ページのスクリーンショット](/tutorial/images/aad-redirect-uris.png)

1. <span data-ttu-id="71668-126">[**既定のクライアントの種類**] セクションを探し、[アプリケーションを**パブリッククライアントとして扱う**] を [**はい**] に変更して、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="71668-126">Locate the **Default client type** section and change the **Treat application as a public client** toggle to **Yes**, then choose **Save**.</span></span>

    ![[既定のクライアントの種類] セクションのスクリーンショット](/tutorial/images/aad-default-client-type.png)

## <a name="configure-the-sample"></a><span data-ttu-id="71668-128">サンプルを構成する</span><span class="sxs-lookup"><span data-stu-id="71668-128">Configure the sample</span></span>

1. <span data-ttu-id="71668-129">ファイルの`appsettings.json.example`名前を`appsettings.json`に変更します。</span><span class="sxs-lookup"><span data-stu-id="71668-129">Rename the `appsettings.json.example` file to `appsettings.json`.</span></span>
1. <span data-ttu-id="71668-130">`appsettings.json`ファイルを編集し、次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="71668-130">Edit the `appsettings.json` file and make the following changes.</span></span>
    1. <span data-ttu-id="71668-131">を`YOUR_APP_ID_HERE`アプリ登録ポータルで取得した**アプリケーション Id**に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="71668-131">Replace `YOUR_APP_ID_HERE` with the **Application Id** you got from the App Registration Portal.</span></span>

## <a name="build-and-run-the-sample"></a><span data-ttu-id="71668-132">サンプルの構築と実行</span><span class="sxs-lookup"><span data-stu-id="71668-132">Build and run the sample</span></span>

<span data-ttu-id="71668-133">コマンドラインインターフェイス (CLI) で、プロジェクトディレクトリに移動し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="71668-133">In your command-line interface (CLI), navigate to the project directory and run the following commands.</span></span>

```Shell
dotnet restore
dotnet build
dotnet run
```