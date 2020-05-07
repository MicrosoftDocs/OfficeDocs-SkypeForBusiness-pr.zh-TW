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
description: 了解新式驗證如何運作、如何切換帳戶，以及如何疑難排解新式驗證。
ms.custom: seo-marvel-apr2020
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 344cf0d38926af200f4d92b664761d2c8868df57
ms.sourcegitcommit: c3f44fccdbd9178d30b52bb0db6f6d31a6dd174b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2020
ms.locfileid: "44139136"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="09e2a-103">使用新式驗證登入 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="09e2a-103">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="09e2a-104">Microsoft Teams 使用新式驗證讓登入體驗更加簡單可靠。</span><span class="sxs-lookup"><span data-stu-id="09e2a-104">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="09e2a-105">若要瞭解使用者如何登入 Teams，請閱讀[登入 Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)。</span><span class="sxs-lookup"><span data-stu-id="09e2a-105">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="09e2a-106">新式驗證的運作方式</span><span class="sxs-lookup"><span data-stu-id="09e2a-106">How modern authentication works</span></span>

<span data-ttu-id="09e2a-107">新式驗證是一種程序，可讓 Teams 知道使用者已經在別處輸入其認證 (例如他們的工作電子郵件和密碼)，因此不需要再次輸入就能啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="09e2a-107">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="09e2a-108">這項體驗會根據幾項因素而有所不同，例如使用者是在 Windows 或在 Mac 上工作。</span><span class="sxs-lookup"><span data-stu-id="09e2a-108">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="09e2a-109">它也會根據您的組織是啟用單一要素驗證還是多重要素驗證而有所不同 (多重要素驗證通常牽涉到透過手機，提供唯一的驗證碼、輸入 PIN 或呈現指紋來驗證認證)。</span><span class="sxs-lookup"><span data-stu-id="09e2a-109">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="09e2a-110">以下是每個新式驗證案例的摘要。</span><span class="sxs-lookup"><span data-stu-id="09e2a-110">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="09e2a-111">Windows 使用者</span><span class="sxs-lookup"><span data-stu-id="09e2a-111">Windows users</span></span> 

- <span data-ttu-id="09e2a-112">如果使用者已透過 Office 365 企業版帳戶登入其他 Office 應用程式，當他們啟動 Teams 時，就可以直接進入應用程式。</span><span class="sxs-lookup"><span data-stu-id="09e2a-112">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="09e2a-113">不需要輸入認證。</span><span class="sxs-lookup"><span data-stu-id="09e2a-113">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="09e2a-114">如果使用者未登入其 Office 365 企業版帳戶，當他們啟動 Teams 時，系統會要求他們提供單一要素或多重要素驗證 (SFA 或 MFA)，取決於您的組織決定要採取的程序。</span><span class="sxs-lookup"><span data-stu-id="09e2a-114">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="09e2a-115">如果使用者登入加入網域的電腦，當他們啟動 Teams 時，系統可能會要求他們執行一個進一步的驗證步驟，視您的組織是否選擇要求 MFA 或他們的電腦是否要求 MFA 才能登入而定。</span><span class="sxs-lookup"><span data-stu-id="09e2a-115">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="09e2a-116">如果使用者的電腦要求 MFA 才能登入，當他們開啟 Teams 時，應用程式會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="09e2a-116">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

- <span data-ttu-id="09e2a-117">如果使用者登入加入網域的電腦，但是您**不希望 Teams 登入畫面預先填入其使用者名稱**，系統管理員可以設定下列 Windows 登錄，關閉預先填入使用者名稱 (UPN) 的功能：</span><span class="sxs-lookup"><span data-stu-id="09e2a-117">If users are signed in to a domain-joined computer and you **don't want their user name pre-populated on the Teams sign-in screen**, admins can set the following Windows registry to turn off pre-population of the user name (UPN):</span></span>

  <span data-ttu-id="09e2a-118">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="09e2a-118">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="09e2a-119">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="09e2a-119">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="09e2a-120">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="09e2a-120">0x00000001 (1)</span></span>

  <span data-ttu-id="09e2a-121">如果執行 Outlook 2013 或2016，請參閱 [更新以跳過 Outlook 2016 和 2013 中使用者主要名稱 (UPN) 查閱](https://support.microsoft.com/help/4022165/update-to-skip-user-principal-name-upn-lookup-in-outlook-2016-and-2013)</span><span class="sxs-lookup"><span data-stu-id="09e2a-121">If you're running Outlook 2013 or 2016, read [Update to skip the user principal name (UPN) lookup in Outlook 2016 and 2013](https://support.microsoft.com/help/4022165/update-to-skip-user-principal-name-upn-lookup-in-outlook-2016-and-2013)</span></span>

    > [!NOTE]
    > <span data-ttu-id="09e2a-122">針對以 ".local" 或 ".corp" 結尾的使用者名稱，略過或忽略使用者名稱預先填入的功能依預設會開啟，因此您不需要設定登錄機碼就能關閉此功能。</span><span class="sxs-lookup"><span data-stu-id="09e2a-122">Skipping or ignoring user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span> 


### <a name="mac-users"></a><span data-ttu-id="09e2a-123">Mac 使用者</span><span class="sxs-lookup"><span data-stu-id="09e2a-123">Mac users</span></span> 

<span data-ttu-id="09e2a-124">使用者啟動 Teams 時，他們的電腦無法從他們的 Office 365 企業版帳戶或其他任何 Office 應用程式中提取認證。</span><span class="sxs-lookup"><span data-stu-id="09e2a-124">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="09e2a-125">而是會顯示提示詢問他們進行 SFA 或 MFA (視您組織的設定而定)。</span><span class="sxs-lookup"><span data-stu-id="09e2a-125">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="09e2a-126">使用者輸入認證後，就不需要再次提供這些認證。</span><span class="sxs-lookup"><span data-stu-id="09e2a-126">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="09e2a-127">從這時起，只要他們在同一部電腦上工作，Teams 就會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="09e2a-127">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="09e2a-128">完成新式驗證後切換帳戶</span><span class="sxs-lookup"><span data-stu-id="09e2a-128">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="09e2a-129">如果使用者正在加入網域的電腦 (例如，如果其租用戶已啟用 Kerberos) 上工作，他們在完成新式驗證之後，就無法切換使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="09e2a-129">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="09e2a-130">如果使用者不是在加入網域的電腦上工作，他們就可以切換帳戶。</span><span class="sxs-lookup"><span data-stu-id="09e2a-130">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a><span data-ttu-id="09e2a-131">完成新式驗證後登出 Teams</span><span class="sxs-lookup"><span data-stu-id="09e2a-131">Signing out of Teams after completing modern authentication</span></span>
<span data-ttu-id="09e2a-132">若要登出 Teams，使用者可以按一下應用程式頂端的個人檔案圖片，然後選取 **[登出]**，也可以在其工作列中的應用程式圖示上按一下滑鼠右鍵，然後選取 **[登出]**。登出 Teams 之後，必須再次輸入認證，才能啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="09e2a-132">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="urls-and-ip-address-ranges"></a><span data-ttu-id="09e2a-133">URL 和 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="09e2a-133">URLs and IP address ranges</span></span>
<span data-ttu-id="09e2a-134">Teams 需要連線到網際網路。</span><span class="sxs-lookup"><span data-stu-id="09e2a-134">Teams requires connectivity to the Internet.</span></span> <span data-ttu-id="09e2a-135">若要瞭解客戶在 Office 365 方案、政府和其他雲端中使用 Teams 能夠連線的端點，請參閱 [Office 365 URL 和 IP 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="09e2a-135">To understand endpoints that should be reachable for customers using Teams in Office 365 plans, Government and other clouds, read [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="09e2a-136">Teams 目前需要讓所有使用者存取 (TCP 通訊埠 443) 連線到 Google ssl.gstatic.com 服務 (https://ssl.gstatic.com)。即使您沒有使用 Gstatic 亦同。</span><span class="sxs-lookup"><span data-stu-id="09e2a-136">Teams presently requires access (TCP port 443) to the Google ssl.gstatic.com service (https://ssl.gstatic.com) for all users; this is true even if you're not using Gstatic.</span></span> <span data-ttu-id="09e2a-137">Teams 很快會移除此要求 (2020 年初)，我們到時候也會更新本文。</span><span class="sxs-lookup"><span data-stu-id="09e2a-137">Teams will remove this requirement soon (early 2020), and we'll update this article accordingly at that time.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="09e2a-138">疑難排解新式驗證</span><span class="sxs-lookup"><span data-stu-id="09e2a-138">Troubleshooting modern authentication</span></span>

<span data-ttu-id="09e2a-139">每個使用 Teams 的組織都能使用新式驗證，因此如果使用者無法完成程序，您的網域或組織的 Office 365 企業版帳戶可能有問題。</span><span class="sxs-lookup"><span data-stu-id="09e2a-139">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="09e2a-140">如需詳細資訊，請參閱[為何我無法登入 Microsoft Teams？](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span><span class="sxs-lookup"><span data-stu-id="09e2a-140">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span></span>

