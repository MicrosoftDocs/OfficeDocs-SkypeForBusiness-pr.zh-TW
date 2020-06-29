---
title: 使用新式驗證登入 Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 了解新式驗證如何運作、如何切換帳戶，以及如何疑難排解新式驗證。 包含如何在登入時告訴 Teams 忽略預先填入的使用者名稱 (UPN)。
ms.custom: seo-marvel-apr2020
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0189c6072840582854b276f0c0116e03fcaff3c0
ms.sourcegitcommit: 0979fae58ecd713f8317ed99caae015b5cc2c8e4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2020
ms.locfileid: "44877814"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="364df-104">使用新式驗證登入 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="364df-104">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="364df-105">Microsoft 建議組織使用最新版本的 Windows 10，內含有混合式網域加入或 Azure AD 加入設定。</span><span class="sxs-lookup"><span data-stu-id="364df-105">Microsoft recommends that organizations use recent versions of Windows 10 with either Hybrid Domain Join or Azure AD Join configuration.</span></span> <span data-ttu-id="364df-106">這可確保在 Windows 網頁帳戶管理員中已將使用者的帳戶準備好，進而讓您以單一的方式登入 Teams 和其他 Microsoft 應用程式。</span><span class="sxs-lookup"><span data-stu-id="364df-106">This ensures that users’ accounts are primed in Windows’ Web Account Manager, which in turns enables single sign-on to Teams and other Microsoft applications.</span></span> <span data-ttu-id="364df-107">這可提供更好的使用者體驗 (無訊息式登入) 和加強的安全性狀況。</span><span class="sxs-lookup"><span data-stu-id="364df-107">This provides a better user experience (silent sign-in) and a better security posture.</span></span>

<span data-ttu-id="364df-108">Microsoft Teams 使用新式驗證讓登入體驗更加簡單可靠。</span><span class="sxs-lookup"><span data-stu-id="364df-108">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="364df-109">若要瞭解使用者如何登入 Teams，請閱讀[登入 Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)。</span><span class="sxs-lookup"><span data-stu-id="364df-109">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="364df-110">新式驗證的運作方式</span><span class="sxs-lookup"><span data-stu-id="364df-110">How modern authentication works</span></span>

<span data-ttu-id="364df-111">新式驗證是一種程序，可讓 Teams 知道使用者已經在別處輸入其認證 (例如他們的工作電子郵件和密碼)，因此不需要再次輸入就能啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="364df-111">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="364df-112">這項體驗會根據幾項因素而有所不同，例如使用者是在 Windows 或在 Mac 上工作。</span><span class="sxs-lookup"><span data-stu-id="364df-112">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="364df-113">它也會根據您的組織是啟用單一要素驗證還是多重要素驗證而有所不同 (多重要素驗證通常牽涉到透過手機，提供唯一的驗證碼、輸入 PIN 或呈現指紋來驗證認證)。</span><span class="sxs-lookup"><span data-stu-id="364df-113">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="364df-114">以下是每個新式驗證案例的摘要。</span><span class="sxs-lookup"><span data-stu-id="364df-114">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="364df-115">Windows 使用者</span><span class="sxs-lookup"><span data-stu-id="364df-115">Windows users</span></span>

- <span data-ttu-id="364df-116">如果使用者已透過他們的公司或學校帳戶登入 Windows 或其他 Office 應用程式，當他們啟動 Teams 時，就可以直接進入應用程式。</span><span class="sxs-lookup"><span data-stu-id="364df-116">If users have already signed in to Windows or to other Office apps with their work or school account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="364df-117">不需要再輸入認證。</span><span class="sxs-lookup"><span data-stu-id="364df-117">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="364df-118">Microsoft 建議使用 Windows 10 版本 1903 或更新版本，以獲得最佳的單一登入體驗。</span><span class="sxs-lookup"><span data-stu-id="364df-118">Microsoft recommends using Windows 10 version 1903 or later for the best Single Sign-On experience.</span></span>

- <span data-ttu-id="364df-119">如果使用者未登入他們的 Microsoft 公司或學校帳戶，當他們啟動 Teams 時，系統會要求他們提供單一要素或多重要素驗證 (SFA 或 MFA)，取決於您的組織決定要採取的程序。</span><span class="sxs-lookup"><span data-stu-id="364df-119">If users are not signed in to their Microsoft work or school account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="364df-120">如果使用者登入加入網域的電腦，當他們啟動 Teams 時，系統可能會要求他們執行一個進一步的驗證步驟，視您的組織是否選擇要求 MFA 或他們的電腦是否要求 MFA 才能登入而定。</span><span class="sxs-lookup"><span data-stu-id="364df-120">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="364df-121">如果使用者的電腦要求 MFA 才能登入，當他們開啟 Teams 時，應用程式會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="364df-121">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

- <span data-ttu-id="364df-122">在已加入網域的電腦上，如果無法使用 SSO，Teams 可能會使用使用者主體名稱 (UPN) 預先填入其登入畫面。</span><span class="sxs-lookup"><span data-stu-id="364df-122">On Domain joined PCs, when SSO isn't possible Teams may pre-fill its login screen with the user principal name (UPN).</span></span> <span data-ttu-id="364df-123">您可能不會想要這種情況發生，特別是如果您的組織在內部部署和 Azure Active Directory 中使用不同的 UPN。</span><span class="sxs-lookup"><span data-stu-id="364df-123">There are cases where you may not want this, especially if your organization uses different UPNs on-premises and in Azure Active Directory.</span></span> <span data-ttu-id="364df-124">如果是這樣，您可以使用下列 Windows 登錄機碼來關閉 UPN 的預先填入：</span><span class="sxs-lookup"><span data-stu-id="364df-124">If that's the case, you can use the following Windows registry key to turn off pre-population of the UPN:</span></span>

  <span data-ttu-id="364df-125">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="364df-125">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="364df-126">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="364df-126">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="364df-127">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="364df-127">0x00000001 (1)</span></span>

    > [!NOTE]
    > <span data-ttu-id="364df-128">針對以 ".local" 或 ".corp" 結尾的使用者名稱，略過或忽略使用者名稱預先填入的功能依預設會開啟，因此您不需要設定登錄機碼就能關閉此功能。</span><span class="sxs-lookup"><span data-stu-id="364df-128">Skipping or ignoring user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span>


### <a name="mac-users"></a><span data-ttu-id="364df-129">Mac 使用者</span><span class="sxs-lookup"><span data-stu-id="364df-129">Mac users</span></span>

<span data-ttu-id="364df-130">在 MacOS 上，Teams 會提示使用者輸入其使用者名稱和認證，並根據貴組織的設定，可能會提示多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="364df-130">On MacOS, Teams will prompt users to enter their username and credentials and may prompt for multi-factor authentication depending on your organization's settings.</span></span> <span data-ttu-id="364df-131">使用者輸入認證後，就不需要再次提供這些認證。</span><span class="sxs-lookup"><span data-stu-id="364df-131">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="364df-132">從這時起，只要他們在同一部電腦上工作，Teams 就會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="364df-132">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="teams-for-ios-and-android-users"></a><span data-ttu-id="364df-133">適合 iOS 和 Android 使用者的 Teams</span><span class="sxs-lookup"><span data-stu-id="364df-133">Teams for iOS and Android users</span></span>

<span data-ttu-id="364df-134">登入後，行動使用者將會看到目前登入或先前已在其裝置上登入的所有 Microsoft 365 帳戶清單。</span><span class="sxs-lookup"><span data-stu-id="364df-134">Upon sign in, mobile users will see a list of all the Microsoft 365 accounts that are either currently signed in or were previously signed in on their device.</span></span> <span data-ttu-id="364df-135">使用者可以點擊任何帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="364df-135">Users can tap on any of the accounts to sign in.</span></span> <span data-ttu-id="364df-136">以行動裝置登入會有下列兩種案例：</span><span class="sxs-lookup"><span data-stu-id="364df-136">There are two scenarios for mobile sign in:</span></span>
    
1. <span data-ttu-id="364df-137">如果選取的帳戶目前已登入其他 Office 365 或 Microsoft 365 app，系統會將該使用者直接移至 Teams。</span><span class="sxs-lookup"><span data-stu-id="364df-137">If the selected account is currently signed in to other Office 365 or Microsoft 365 apps, then the user will be taken straight to Teams.</span></span> <span data-ttu-id="364df-138">使用者不需要再輸入認證。</span><span class="sxs-lookup"><span data-stu-id="364df-138">There is no need for the user to enter their credentials.</span></span>
    
2. <span data-ttu-id="364df-139">如果使用者未登入其 Microsoft 365 帳戶的其他位置，系統會要求他們提供單一要素或多重要素驗證 (SFA 或 MFA)，視貴組織針對 [行動裝置登入原則] 設定的內容而定。</span><span class="sxs-lookup"><span data-stu-id="364df-139">If user isn't signed in to their Microsoft 365 account anywhere else, they will be asked to provide single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has configured for mobile sign in policies.</span></span>

> [!NOTE]
> <span data-ttu-id="364df-140">若要讓使用者體驗本節所述的 [登入體驗]，他們的裝置必須是能夠執行 iOS 版2.0.13 （組建2020061704）或更新版本，或為 Android 版的 Teams 版本 1416/1.0.0.2020061702 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="364df-140">For users to experience the sign on experience as described in this section, their devices must be running Teams for iOS version 2.0.13 (build 2020061704) or later, or Teams for Android version 1416/1.0.0.2020061702 or later.</span></span>


### <a name="adding-multiple-accounts-to-teams"></a><span data-ttu-id="364df-141">在 Teams 中新增多個帳戶</span><span class="sxs-lookup"><span data-stu-id="364df-141">Adding multiple accounts to Teams</span></span>

<span data-ttu-id="364df-142">IOS 和 Android 版的 Teams 支援將多個帳戶從單一裝置新增至 Teams。</span><span class="sxs-lookup"><span data-stu-id="364df-142">Teams for iOS and Android supports adding multiple accounts from a single device to Teams.</span></span> <span data-ttu-id="364df-143">下列影像顯示如何在 Teams 中新增多個帳戶。</span><span class="sxs-lookup"><span data-stu-id="364df-143">The following images show how users can add multiple accounts in Teams.</span></span>
    
:::image type="content" source="media/sign-in-multiple-accounts.png" alt-text="在 Teams 中新增多個帳戶":::

### <a name="use-enterprise-mobility-management-to-control-which-accounts-can-sign-in-to-teams"></a><span data-ttu-id="364df-145">使用企業行動管理來控制哪些帳戶可以登入 Teams</span><span class="sxs-lookup"><span data-stu-id="364df-145">Use enterprise mobility management to control which accounts can sign in to Teams</span></span>

<span data-ttu-id="364df-146">IOS 和 Android 版 Teams 提供 IT 系統管理員將帳戶設定推入 Microsoft 365 帳戶的功能。</span><span class="sxs-lookup"><span data-stu-id="364df-146">Teams for iOS and Android offers IT administrators the ability to push account configurations to Microsoft 365 accounts.</span></span> <span data-ttu-id="364df-147">這項功能可與任何使用 iOS [受控應用程式設定 ](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html) 通道或 Android 的 [Android 企業](https://developer.android.com/work/managed-configurations) 通道的行動裝置管理 (MDM) 提供者相配合。</span><span class="sxs-lookup"><span data-stu-id="364df-147">This capability works with any Mobile Device Management (MDM) provider who uses the [Managed App Configuration](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html) channel for iOS or the [Android Enterprise](https://developer.android.com/work/managed-configurations) channel for Android.</span></span>

<span data-ttu-id="364df-148">針對註冊于 Microsoft Intune 的使用者，您可以在 Azure 入口網站中使用 Intune 部署帳戶配置設定。</span><span class="sxs-lookup"><span data-stu-id="364df-148">For users enrolled in Microsoft Intune, you can deploy the account configuration settings using Intune in the Azure Portal.</span></span>

<span data-ttu-id="364df-149">當 MDM 提供者設定好帳戶設定之後，且使用者註冊其裝置之後，iOS 和 Android 版 Teams 將只會在 Teams 登入頁面上顯示允許的帳戶。</span><span class="sxs-lookup"><span data-stu-id="364df-149">Once account setup configuration has been setup in the MDM provider, and after the user enrolls their device, on the login pgae, Teams for iOS and Android will only show the allowed account(s) on the Teams login page.</span></span> <span data-ttu-id="364df-150">使用者可以點擊此頁面中任何允許的帳戶以登入。</span><span class="sxs-lookup"><span data-stu-id="364df-150">The user can tap on any of the allowed accounts on this page to sign in.</span></span>

<span data-ttu-id="364df-151">在受管理的裝置的 Azure Intune 入口網站中設定下列設定參數。</span><span class="sxs-lookup"><span data-stu-id="364df-151">Set the following configuration parameters in the Azure Intune portal for managed devices.</span></span>


|<span data-ttu-id="364df-152">平台</span><span class="sxs-lookup"><span data-stu-id="364df-152">Platform</span></span> |<span data-ttu-id="364df-153">機碼</span><span class="sxs-lookup"><span data-stu-id="364df-153">Key</span></span>  |<span data-ttu-id="364df-154">值</span><span class="sxs-lookup"><span data-stu-id="364df-154">Value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="364df-155">iOS</span><span class="sxs-lookup"><span data-stu-id="364df-155">iOS</span></span>     |  <span data-ttu-id="364df-156">**IntuneMAMAllowedAccountsOnly**</span><span class="sxs-lookup"><span data-stu-id="364df-156">**IntuneMAMAllowedAccountsOnly**</span></span>       | <span data-ttu-id="364df-157">**已啟用**: 唯一允許的帳戶是由 IntuneMAMUPN 機碼所定義的受管用戶帳戶。</span><span class="sxs-lookup"><span data-stu-id="364df-157">**Enabled**: The only account allowed is the managed user account defined by the IntuneMAMUPN key.</span></span><br> <span data-ttu-id="364df-158">**已停用** (或與 **啟用**不區分大小寫的任何值): 允許任何帳戶。</span><span class="sxs-lookup"><span data-stu-id="364df-158">**Disabled** (or any value that is not a case insensitive match to **Enabled**): Any account is allowed.</span></span>        |
|<span data-ttu-id="364df-159">iOS</span><span class="sxs-lookup"><span data-stu-id="364df-159">iOS</span></span>     |   <span data-ttu-id="364df-160">**IntuneMAMUPN**</span><span class="sxs-lookup"><span data-stu-id="364df-160">**IntuneMAMUPN**</span></span>      |   <span data-ttu-id="364df-161">允許登入 Teams 的帳戶 UPN。</span><span class="sxs-lookup"><span data-stu-id="364df-161">UPN of the account allowed to sign in to Teams.</span></span><br> <span data-ttu-id="364df-162">如果您是 Intune 註冊的裝置，可以使用 {{userprincipalname}} 符號來代表已註冊的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="364df-162">For Intune enrolled devices, the {{userprincipalname}} token may be used to represent the enrolled user account.</span></span>       |
|<span data-ttu-id="364df-163">Android</span><span class="sxs-lookup"><span data-stu-id="364df-163">Android</span></span>     |<span data-ttu-id="364df-164">**com.microsoft.intune.mam.AllowedAccountUPNs**</span><span class="sxs-lookup"><span data-stu-id="364df-164">**com.microsoft.intune.mam.AllowedAccountUPNs**</span></span>         |    <span data-ttu-id="364df-165">只有允許帳戶是由此編碼定義的受管用戶帳戶。</span><span class="sxs-lookup"><span data-stu-id="364df-165">Only account(s) allowed are the managed user account(s) defined by this key.</span></span><br> <span data-ttu-id="364df-166">一或多個分號 [;]- delmited UPNs。</span><span class="sxs-lookup"><span data-stu-id="364df-166">One or more semi-colon [;]- delmited UPNs.</span></span><br> <span data-ttu-id="364df-167">如果您是 Intune 註冊的裝置，可以使用 {{userprincipalname}} 符號來代表已註冊的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="364df-167">For Intune enrolled devices, the {{userprincipalname}} token may be used to represent the enrolled user account.</span></span>

<span data-ttu-id="364df-168">當帳戶設定完成之後， Teams 會限制登入的能力，因此只有登入的裝置上允許的帳戶才能取得存取權。</span><span class="sxs-lookup"><span data-stu-id="364df-168">Once the account setup configuration has been set, Teams will restrict the ability to sign in, so that only allowed accounts on enrolled devices will be granted access.</span></span>

<span data-ttu-id="364df-169">若要為受管理的 iOS/iPadOS 裝置建立應用程式設定原則，請參閱 [新增受管理的 iOS/iPadOS 裝置 app 設定原則](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-ios)。</span><span class="sxs-lookup"><span data-stu-id="364df-169">To create an app configuration policy for managed iOS/iPadOS devices, see [Add app configuration policies for managed iOS/iPadOS devices](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-ios).</span></span>

<span data-ttu-id="364df-170">若要為受管理的 Android 裝置建立應用程式設定原則，請參閱 [新增受管理的 Android 裝置應用程式設定原則](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-android)。</span><span class="sxs-lookup"><span data-stu-id="364df-170">To create an app configuration policy for managed Android devices, see [Add app configuration policies for managed Android devices](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-android).</span></span>


## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="364df-171">完成新式驗證後切換帳戶</span><span class="sxs-lookup"><span data-stu-id="364df-171">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="364df-172">如果使用者正在加入網域的電腦 (例如，如果其租用戶已啟用 Kerberos) 上工作，他們在完成新式驗證之後，就無法切換使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="364df-172">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="364df-173">如果使用者不是在加入網域的電腦上工作，他們就可以切換帳戶。</span><span class="sxs-lookup"><span data-stu-id="364df-173">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a><span data-ttu-id="364df-174">完成新式驗證後登出 Teams</span><span class="sxs-lookup"><span data-stu-id="364df-174">Signing out of Teams after completing modern authentication</span></span>

<span data-ttu-id="364df-175">若要登出 Teams，使用者可以按一下應用程式頂端的個人檔案圖片，然後選取 **[登出]**，也可以在其工作列中的應用程式圖示上按一下滑鼠右鍵，然後選取 **[登出]**。登出 Teams 之後，必須再次輸入認證，才能啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="364df-175">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

### <a name="signing-out-of-teams-for-ios-and-android"></a><span data-ttu-id="364df-176">登出 iOS 和 Android 的 Teams</span><span class="sxs-lookup"><span data-stu-id="364df-176">Signing out of Teams for iOS and Android</span></span>

<span data-ttu-id="364df-177">行動使用者可以移至功能表，並選擇 **[更多]** 功能表，然後選擇 **[登出]**，以登出 Teams。一旦登出，使用者則需在下一次啟動該應用程式時，重新輸入認證。</span><span class="sxs-lookup"><span data-stu-id="364df-177">Mobile users can sign out of Teams by going to the menu and choosing the **More** menu, and then choosing **Sign out**. Once signed out, users will need to re-enter their credentials the next time they launch the app.</span></span>

> [!NOTE]
> <span data-ttu-id="364df-178">Android 版 Teams 使用單一登入（SSO）來簡化登入體驗。</span><span class="sxs-lookup"><span data-stu-id="364df-178">Teams for Android uses single sign-on (SSO) to simplify the sign in experience.</span></span> <span data-ttu-id="364df-179">使用者除了 Team 以外，還應務必登出 **所有** 的 Microsoft 應用程式，以便完全登出 Android 平臺。</span><span class="sxs-lookup"><span data-stu-id="364df-179">Users should make sure to log out of **all** Microsoft apps, in addition to Teams, in order to completely log out on the Android platform.</span></span>

## <a name="urls-and-ip-address-ranges"></a><span data-ttu-id="364df-180">URL 和 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="364df-180">URLs and IP address ranges</span></span>

<span data-ttu-id="364df-181">Teams 需要連線到網際網路。</span><span class="sxs-lookup"><span data-stu-id="364df-181">Teams requires connectivity to the Internet.</span></span> <span data-ttu-id="364df-182">若要瞭解客戶在 Office 365 方案、政府和其他雲端中使用 Teams 能夠連線的端點，請參閱 [Office 365 URL 和 IP 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="364df-182">To understand endpoints that should be reachable for customers using Teams in Office 365 plans, Government and other clouds, read [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="364df-183">Teams 目前需要讓所有使用者存取 (TCP 通訊埠 443) 連線到 Google ssl.gstatic.com 服務 (<https://ssl.gstatic.com)>。即使您沒有使用 Gstatic 亦同。</span><span class="sxs-lookup"><span data-stu-id="364df-183">Teams presently requires access (TCP port 443) to the Google ssl.gstatic.com service (<https://ssl.gstatic.com)> for all users; this is true even if you're not using Gstatic.</span></span> <span data-ttu-id="364df-184">Teams 很快會移除此要求 (2020 年初)，我們到時候也會更新本文。</span><span class="sxs-lookup"><span data-stu-id="364df-184">Teams will remove this requirement soon (early 2020), and we'll update this article accordingly at that time.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="364df-185">疑難排解新式驗證</span><span class="sxs-lookup"><span data-stu-id="364df-185">Troubleshooting modern authentication</span></span>

<span data-ttu-id="364df-186">每個使用 Teams 的組織都能使用新式驗證，因此如果使用者無法完成程序，您的網域或組織的 Microsoft 公司或學校帳戶可能有問題。</span><span class="sxs-lookup"><span data-stu-id="364df-186">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Microsoft work or school account.</span></span>

<span data-ttu-id="364df-187">如需詳細資訊，請參閱[為何我無法登入 Microsoft Teams？](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span><span class="sxs-lookup"><span data-stu-id="364df-187">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span></span>
