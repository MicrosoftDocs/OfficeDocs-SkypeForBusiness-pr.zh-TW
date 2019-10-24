---
title: 使用新式驗證登入 Microsoft 團隊
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 如何使用新式驗證登入 Microsoft 團隊。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5698058cbfecd62f92cfe9f198657f7c280deff
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2019
ms.locfileid: "37568681"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="adfae-103">使用新式驗證登入 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="adfae-103">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="adfae-104">Microsoft 團隊使用新式驗證來輕鬆且安全地保持登入體驗。</span><span class="sxs-lookup"><span data-stu-id="adfae-104">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="adfae-105">若要查看使用者如何登入小組，請閱讀登[入小組](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)。</span><span class="sxs-lookup"><span data-stu-id="adfae-105">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="adfae-106">新式驗證的運作方式</span><span class="sxs-lookup"><span data-stu-id="adfae-106">How modern authentication works</span></span>

<span data-ttu-id="adfae-107">新式驗證是一個可讓團隊知道使用者已在其他位置輸入其認證（例如其公司電子郵件和密碼）的程式，因此不需要再次輸入它們即可啟動 app。</span><span class="sxs-lookup"><span data-stu-id="adfae-107">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="adfae-108">體驗會根據幾個因素而有所不同，就像使用者是在 Windows 或在 Mac 上運作一樣。</span><span class="sxs-lookup"><span data-stu-id="adfae-108">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="adfae-109">根據您的組織是否已啟用單一要素驗證或多重要素驗證（多重要素驗證），它也會根據您的組織，提供唯一的程式碼、輸入 PIN，或呈現指紋）。</span><span class="sxs-lookup"><span data-stu-id="adfae-109">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="adfae-110">以下是每個新式驗證案例的結尾。</span><span class="sxs-lookup"><span data-stu-id="adfae-110">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="adfae-111">Windows 使用者</span><span class="sxs-lookup"><span data-stu-id="adfae-111">Windows users</span></span> 

- <span data-ttu-id="adfae-112">如果使用者已透過其 Office 365 企業帳戶登入其他 Office 應用程式，當他們啟動團隊時，他們會直接移至應用程式。</span><span class="sxs-lookup"><span data-stu-id="adfae-112">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="adfae-113">您不需要他們輸入其認證。</span><span class="sxs-lookup"><span data-stu-id="adfae-113">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="adfae-114">如果使用者未在其他位置登入 Office 365 企業版帳戶，當他們開始團隊時，系統會要求他們提供單一要素或多重要素驗證（SFA 或 MFA），這取決於貴組織決定要需要處理的程式。</span><span class="sxs-lookup"><span data-stu-id="adfae-114">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="adfae-115">如果使用者已登入加入網域的電腦，當他們啟動團隊時，可能會要求您執行一個更驗證步驟，視貴組織選擇要要求 MFA 或其電腦是否已需要 MFA 登入而定。</span><span class="sxs-lookup"><span data-stu-id="adfae-115">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="adfae-116">如果他們的電腦已要求 MFA 登入，當他們開啟 [小組] 時，應用程式就會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="adfae-116">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

### <a name="mac-users"></a><span data-ttu-id="adfae-117">Mac 使用者</span><span class="sxs-lookup"><span data-stu-id="adfae-117">Mac users</span></span> 

<span data-ttu-id="adfae-118">當使用者開始團隊時，其電腦將無法從其 Office 365 企業版帳戶或其他任何 Office 應用程式中提取其認證。</span><span class="sxs-lookup"><span data-stu-id="adfae-118">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="adfae-119">相反地，他們會看到要求他們進行 SFA 或 MFA 的提示（視貴組織的設定而定）。</span><span class="sxs-lookup"><span data-stu-id="adfae-119">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="adfae-120">使用者輸入其認證之後，就不需要再提供這些認證。</span><span class="sxs-lookup"><span data-stu-id="adfae-120">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="adfae-121">從該點開始，團隊會在他們在同一部電腦上工作時自動啟動。</span><span class="sxs-lookup"><span data-stu-id="adfae-121">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="adfae-122">完成新式驗證之後切換帳戶</span><span class="sxs-lookup"><span data-stu-id="adfae-122">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="adfae-123">如果使用者是在加入網域的電腦上工作（例如，如果其租使用者已啟用 Kerberos），則他們在完成新式驗證之後，就無法切換使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="adfae-123">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="adfae-124">如果使用者無法在加入網域的電腦上工作，他們可以切換帳戶。</span><span class="sxs-lookup"><span data-stu-id="adfae-124">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a><span data-ttu-id="adfae-125">在完成新式驗證後登出 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="adfae-125">Signing out of Microsoft Teams after completing modern authentication</span></span>
<span data-ttu-id="adfae-126">若要登出團隊，使用者可以按一下應用程式頂端的個人檔案圖片，**然後選取 [登出]**。他們也可以在其工作列中以滑鼠右鍵按一下應用程式圖示，然後選取 [**登出**]。登出團隊之後，他們需要再次輸入其認證，才能啟動 app。</span><span class="sxs-lookup"><span data-stu-id="adfae-126">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="adfae-127">現代驗證疑難排解</span><span class="sxs-lookup"><span data-stu-id="adfae-127">Troubleshooting modern authentication</span></span>

<span data-ttu-id="adfae-128">每個使用團隊的組織都能使用新式驗證，所以如果使用者無法完成程式，您的網域或貴組織的 Office 365 企業版帳戶可能會有問題。</span><span class="sxs-lookup"><span data-stu-id="adfae-128">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="adfae-129">如需詳細資訊，請參閱[為什麼我無法登入 Microsoft 團隊？](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)。</span><span class="sxs-lookup"><span data-stu-id="adfae-129">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).</span></span>

