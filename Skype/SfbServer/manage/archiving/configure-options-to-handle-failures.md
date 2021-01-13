---
title: 設定封存選項，以處理商務用 Skype Server 中的失敗
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 摘要：瞭解如何在商務用 Skype 伺服器失敗的情況下封鎖 IM 和會議會話，以避免封存。
ms.openlocfilehash: 9a39c5f54fbdd4a738f4e67e7f70ff199a204672
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817673"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a><span data-ttu-id="54d0e-103">設定封存選項，以處理商務用 Skype Server 中的失敗</span><span class="sxs-lookup"><span data-stu-id="54d0e-103">Configure archiving options to handle failures in Skype for Business Server</span></span>

<span data-ttu-id="54d0e-104">**摘要：** 瞭解如何在商務用 Skype 伺服器失敗的情況下封鎖 IM 和會議會話，以防封存。</span><span class="sxs-lookup"><span data-stu-id="54d0e-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server failure that would prevent archiving.</span></span>
  
<span data-ttu-id="54d0e-105">如果您的組織需要封存，您可以在商務用 Skype 伺服器失敗的情況下封鎖 IM 和會議會話，以避免封存。</span><span class="sxs-lookup"><span data-stu-id="54d0e-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="54d0e-106">這有時稱為重要模式。</span><span class="sxs-lookup"><span data-stu-id="54d0e-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="54d0e-107">例如，如果儲存服務發生問題，將會封鎖啟用封存之通訊的使用者的 IM。</span><span class="sxs-lookup"><span data-stu-id="54d0e-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="54d0e-108">IM 和會議會在失敗更正後自動復原。</span><span class="sxs-lookup"><span data-stu-id="54d0e-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="54d0e-109">使用控制台設定重要模式</span><span class="sxs-lookup"><span data-stu-id="54d0e-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="54d0e-110">若要指定是否應該允許通訊會話，以防失敗的原因：</span><span class="sxs-lookup"><span data-stu-id="54d0e-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="54d0e-111">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="54d0e-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="54d0e-112">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="54d0e-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="54d0e-113">在左導覽列中 **，按一下 [\*\*\*\*監視與** 封存]，然後按一下 [封存設定]。</span><span class="sxs-lookup"><span data-stu-id="54d0e-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="54d0e-114">按一下封存設定清單中適當的全域、網站或集區設定名稱，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="54d0e-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="54d0e-115">若要設定當失敗發生時封存的運作方式，請選取或清除 [封存 **失敗時封鎖立即訊息 (IM) 或 web 會議會話** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="54d0e-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="54d0e-116">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="54d0e-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="54d0e-117">使用 Windows PowerShell 設定重要模式</span><span class="sxs-lookup"><span data-stu-id="54d0e-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="54d0e-118">您也可以指定是否應該允許通訊會話，以防因無法使用 **get-csarchivingconfiguration 指令程式** 搭配 BlockOnArchiveFailure 參數進行封存。</span><span class="sxs-lookup"><span data-stu-id="54d0e-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="54d0e-119">例如，下列命令會在封存失敗時停用通訊：</span><span class="sxs-lookup"><span data-stu-id="54d0e-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="54d0e-120">下一個命令會在封存失敗的情況下啟用通訊：</span><span class="sxs-lookup"><span data-stu-id="54d0e-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="54d0e-121">如需詳細資訊，請參閱 [get-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="54d0e-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
  

