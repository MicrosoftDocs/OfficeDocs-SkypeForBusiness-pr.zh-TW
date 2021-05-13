---
title: 從線上連接器商務用 Skype移Teams PowerShell 模組
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 瞭解如何從線上連接器商務用 Skype到 powerShell 模組Teams以管理Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: e788fc8cd31bd6e8754e410132e02829eaa2cad8
ms.sourcegitcommit: 50ec59b454e751d952cde9fd13c8017529d0e1d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2021
ms.locfileid: "52469715"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="ed855-103">從線上連接器商務用 Skype移Teams PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="ed855-103">Migrating from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="ed855-104">TeamsPowerShell 模組提供一組完整的 Cmdlet，Teams直接從 PowerShell 命令列管理資料。</span><span class="sxs-lookup"><span data-stu-id="ed855-104">Teams PowerShell Module provides a complete set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="ed855-105">系統管理員不需要Skype商務用 Online 連接器進行Teams管理。</span><span class="sxs-lookup"><span data-stu-id="ed855-105">Administrators do not require Skype For Business Online Connector for their Teams administration.</span></span>

> [!NOTE]
> <span data-ttu-id="ed855-106">Teams已于 2021 年 3 月 16 (MC244740 郵件中心張貼公告通知系統管理員;MC250940 于 2021 年 4 月 16 日) 此變更。</span><span class="sxs-lookup"><span data-stu-id="ed855-106">Teams administrator were notified through Message center post (MC244740, dated March 16, 2021; MC250940, dated April 16 2021) about this change.</span></span>
>
> <span data-ttu-id="ed855-107">TeamsPowerShell 模組使用新式驗證，但必須Windows遠端系統管理 (WinRM) 用戶端以允許基本驗證。</span><span class="sxs-lookup"><span data-stu-id="ed855-107">Teams PowerShell Module uses modern authentication, but the underlying Windows Remote Management (WinRM) client must be configured to allow Basic authentication.</span></span> <span data-ttu-id="ed855-108">請參閱[下載並安裝Windows PowerShell，](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1)以取得如何啟用 WinRM for Basic 驗證的指示。</span><span class="sxs-lookup"><span data-stu-id="ed855-108">See [Download and install Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) for instructions on how to enable WinRM for Basic authentication.</span></span>

> [!WARNING]
> <span data-ttu-id="ed855-109">商務用 Skype線上連接器連線將于 2021 年 5 月 17 日拒絕。</span><span class="sxs-lookup"><span data-stu-id="ed855-109">Skype for Business Online Connector connections will be rejected starting May 17, 2021.</span></span> <span data-ttu-id="ed855-110">如需移至 PowerShell 模組的協助和支援，Teams Microsoft 支援服務。</span><span class="sxs-lookup"><span data-stu-id="ed855-110">Please contact Microsoft Support for help and support for migrating to Teams PowerShell Module.</span></span>

## <a name="how-to-migrate"></a><span data-ttu-id="ed855-111">如何遷移</span><span class="sxs-lookup"><span data-stu-id="ed855-111">How to Migrate</span></span>

<span data-ttu-id="ed855-112">從使用線上連接器商務用 Skype移Teams PowerShell 模組非常簡單。</span><span class="sxs-lookup"><span data-stu-id="ed855-112">Migrating from using Skype for Business Online Connector to Teams PowerShell module is easy and simple.</span></span> <span data-ttu-id="ed855-113">下列步驟說明如何執行此操作。</span><span class="sxs-lookup"><span data-stu-id="ed855-113">The below steps explains how to do this.</span></span>

1. <span data-ttu-id="ed855-114">安裝最新的 PowerShell Teams模組。</span><span class="sxs-lookup"><span data-stu-id="ed855-114">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="ed855-115">有關步驟，請參閱[在 Powershell Microsoft Teams安裝](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="ed855-115">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="ed855-116">卸載Skype商務用 Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="ed855-116">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="ed855-117">若要這麼做，請在控制台中，前往程式和功能，選取 商務用 Skype **線上，Windows PowerShell模組**，**然後選取卸載**。</span><span class="sxs-lookup"><span data-stu-id="ed855-117">To do this, in Control Panel, go to **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span>
3. <span data-ttu-id="ed855-118">在 PowerShell 腳本中，變更從 ```Import-Module```</span><span class="sxs-lookup"><span data-stu-id="ed855-118">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from</span></span>

    <span data-ttu-id="ed855-119">`SkypeOnlineConnector` 或 `LyncOnlineConnector` `MicrosoftTeams` to 。</span><span class="sxs-lookup"><span data-stu-id="ed855-119">`SkypeOnlineConnector` or `LyncOnlineConnector` to `MicrosoftTeams`.</span></span>

    <span data-ttu-id="ed855-120">例如，變更 `Import-Module -Name SkypeOnlineConnector` 為 `Import-Module -Name MicrosoftTeams` 。</span><span class="sxs-lookup"><span data-stu-id="ed855-120">For example, change `Import-Module -Name SkypeOnlineConnector` to `Import-Module -Name MicrosoftTeams`.</span></span>

4. <span data-ttu-id="ed855-121">使用 Teams PowerShell 模組 2.0 或更新版本時，請更新您參照的 `New-CsOnlineSession` 腳本 `Connect-MicrosoftTeams` 。</span><span class="sxs-lookup"><span data-stu-id="ed855-121">When using Teams PowerShell Module 2.0 or later, update your scripts that refers `New-CsOnlineSession` to `Connect-MicrosoftTeams`.</span></span> <span data-ttu-id="ed855-122">`Import-PsSession`不再需要建立線上遠端 PowerShell 會話商務用 Skype，因為使用 時隱含完成 `Connect-MicrosoftTeams` 。</span><span class="sxs-lookup"><span data-stu-id="ed855-122">`Import-PsSession` is no longer required to establish a Skype for Business Online Remote PowerShell Session as that is done implicit when using `Connect-MicrosoftTeams`.</span></span>

    ```powershell
       # When using the Skype for Business online connector
         Import-Module SkypeForBusinessConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
       # Example getting tenant details
         Get-csTenant
    
       # When using Teams PowerShell Module 2.0 or later
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
       # Example getting tenant details
         Get-csTenant
    
       # Closing the Session when using the Skype for Business online connector
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # Disconnecting from Teams PowerShell Module 
         Disconnect-MicrosoftTeams
    ```

## <a name="online-support"></a><span data-ttu-id="ed855-123">線上支援</span><span class="sxs-lookup"><span data-stu-id="ed855-123">Online Support</span></span>

<span data-ttu-id="ed855-124">線上啟動服務要求以節省時間。</span><span class="sxs-lookup"><span data-stu-id="ed855-124">Save time by starting your service request online.</span></span> <span data-ttu-id="ed855-125">我們會協助您尋找解決方案，或將您連至技術支援。</span><span class="sxs-lookup"><span data-stu-id="ed855-125">We'll help you find a solution or connect you to technical support.</span></span>
1.  <span data-ttu-id="ed855-126">請前往 系統管理中心 [https://admin.microsoft.com](https://admin.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="ed855-126">Go to the admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span> <span data-ttu-id="ed855-127">如果您收到一則訊息，指出您沒有存取此頁面或執行此動作的許可權，表示您不是系統管理員。神秘擁有我企業中的系統管理員許可權？</span><span class="sxs-lookup"><span data-stu-id="ed855-127">If you get a message that says you don't have permission to access this page or perform this action, then you aren't an admin. Who has admin permissions in my business?</span></span>
2.  <span data-ttu-id="ed855-128">選取需要 **協助嗎**？按鈕。</span><span class="sxs-lookup"><span data-stu-id="ed855-128">Select the **Need help**? button.</span></span>
3.  <span data-ttu-id="ed855-129">在需要 **協助**？窗格，告訴我們您需要哪些協助，然後按 Enter。</span><span class="sxs-lookup"><span data-stu-id="ed855-129">In the **Need help**? pane, tell us what you need help with, and then press Enter.</span></span>
4.  <span data-ttu-id="ed855-130">如果結果沒有説明，請選取 連絡人 **支援**。</span><span class="sxs-lookup"><span data-stu-id="ed855-130">If the results don't help, select **Contact support**.</span></span>
5.  <span data-ttu-id="ed855-131">輸入問題的描述、確認您的連絡人號碼和電子郵件地址、選取您偏好的連絡人方法，然後選取 **連絡人給我**。</span><span class="sxs-lookup"><span data-stu-id="ed855-131">Enter a description of your issue, confirm your contact number and email address, select your preferred contact method, and then select **Contact me**.</span></span> <span data-ttu-id="ed855-132">預期等候時間會以需要協助？窗 格。</span><span class="sxs-lookup"><span data-stu-id="ed855-132">The expected wait time is indicated in the Need help? pane.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ed855-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="ed855-133">Related topics</span></span>

[<span data-ttu-id="ed855-134">安裝 Microsoft Teams Powershell</span><span class="sxs-lookup"><span data-stu-id="ed855-134">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="ed855-135">使用 powerShell Teams管理Teams資料</span><span class="sxs-lookup"><span data-stu-id="ed855-135">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="ed855-136">TeamsPowerShell 版本資訊</span><span class="sxs-lookup"><span data-stu-id="ed855-136">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="ed855-137">Microsoft Teams Cmdlet 參照</span><span class="sxs-lookup"><span data-stu-id="ed855-137">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="ed855-138">商務用 Skype Cmdlet 參照</span><span class="sxs-lookup"><span data-stu-id="ed855-138">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
