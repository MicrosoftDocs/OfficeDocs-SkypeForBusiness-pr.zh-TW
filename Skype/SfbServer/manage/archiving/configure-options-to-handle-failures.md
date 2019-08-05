---
title: 在商務用 Skype Server 中設定封存選項來處理失敗
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: '摘要: 瞭解如何在商務用 Skype 伺服器發生故障時封鎖 IM 和會議會話, 以免封存。'
ms.openlocfilehash: 38f79277ff12aa8e716b034e8393a4d8b71cdbba
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190387"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a><span data-ttu-id="efcae-103">在商務用 Skype Server 中設定封存選項來處理失敗</span><span class="sxs-lookup"><span data-stu-id="efcae-103">Configure archiving options to handle failures in Skype for Business Server</span></span>

<span data-ttu-id="efcae-104">**摘要:** 瞭解如何在商務用 Skype 伺服器發生故障時封鎖 IM 和會議會話, 以免封存。</span><span class="sxs-lookup"><span data-stu-id="efcae-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server failure that would prevent archiving.</span></span>
  
<span data-ttu-id="efcae-105">如果您的組織需要進行封存, 您可以在商務用 Skype 伺服器失敗時封鎖 IM 和會議會話, 避免封存。</span><span class="sxs-lookup"><span data-stu-id="efcae-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="efcae-106">這有時稱為 [重要模式]。</span><span class="sxs-lookup"><span data-stu-id="efcae-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="efcae-107">例如, 如果儲存服務發生問題, 系統會封鎖已啟用其通訊功能的使用者的 IM。</span><span class="sxs-lookup"><span data-stu-id="efcae-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="efcae-108">IM 和會議會在更正失敗之後自動復原。</span><span class="sxs-lookup"><span data-stu-id="efcae-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="efcae-109">使用 [控制台] 設定 [重要] 模式</span><span class="sxs-lookup"><span data-stu-id="efcae-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="efcae-110">若要指定是否應允許通訊會話, 以防發生無法進行封存的問題:</span><span class="sxs-lookup"><span data-stu-id="efcae-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="efcae-111">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="efcae-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="efcae-112">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="efcae-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="efcae-113">在左側導覽列中, 按一下 [**監視及**封存], 然後按一下 [封存**配置**]。</span><span class="sxs-lookup"><span data-stu-id="efcae-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="efcae-114">在歸檔設定清單中, 按一下適當的全域、網站或池設定的名稱, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="efcae-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="efcae-115">若要設定在發生失敗時封存的行為方式, 請選取或清除 [**如果封存失敗, 封鎖立即訊息 (IM) 或 web 會議會話**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="efcae-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="efcae-116">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="efcae-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="efcae-117">使用 Windows PowerShell 來設定重要模式</span><span class="sxs-lookup"><span data-stu-id="efcae-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="efcae-118">您也可以在無法使用**CsArchivingConfiguration** Cmdlet 與 BlockOnArchiveFailure 參數的情況下, 指定是否允許通訊會話, 以防進行封存。</span><span class="sxs-lookup"><span data-stu-id="efcae-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="efcae-119">例如, 下列命令會在發生存檔失敗時停用通訊:</span><span class="sxs-lookup"><span data-stu-id="efcae-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="efcae-120">[下一步] 命令會在發生存檔失敗時啟用通訊:</span><span class="sxs-lookup"><span data-stu-id="efcae-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="efcae-121">如需詳細資訊, 請參閱[CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="efcae-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
  

