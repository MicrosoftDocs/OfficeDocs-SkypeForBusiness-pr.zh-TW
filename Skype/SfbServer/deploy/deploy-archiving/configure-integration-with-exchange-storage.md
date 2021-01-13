---
title: 設定商務用 Skype Server 與 Exchange storage 的整合
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 摘要：閱讀此主題以瞭解如何在商務用 Skype Server 中設定與 Exchange 儲存區的整合。
ms.openlocfilehash: 05a0c65aaca54e469f30dd5e732565f6ec0bbb4b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825063"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a><span data-ttu-id="33f10-103">設定商務用 Skype Server 與 Exchange storage 的整合</span><span class="sxs-lookup"><span data-stu-id="33f10-103">Configure integration with Exchange storage for Skype for Business Server</span></span>
 
<span data-ttu-id="33f10-104">**摘要：** 閱讀此主題以瞭解如何在商務用 Skype Server 中設定與 Exchange 儲存區的整合。</span><span class="sxs-lookup"><span data-stu-id="33f10-104">**Summary:** Read this topic to learn how to configure integration with Exchange storage in Skype for Business Server.</span></span>
  
<span data-ttu-id="33f10-105">如果您部署中的所有使用者都使用 Microsoft Exchange 整合，您就不需要為使用者設定商務用 Skype Server 封存原則。</span><span class="sxs-lookup"><span data-stu-id="33f10-105">If you use Microsoft Exchange integration for all users in your deployment, you don't need to configure Skype for Business Server archiving policies for your users.</span></span> <span data-ttu-id="33f10-106">相反地，您可以設定 Exchange In-Place 保留原則，以支援駐留在 Exchange 上之使用者的封存，並將其信箱置於 In-Place 保留狀態。</span><span class="sxs-lookup"><span data-stu-id="33f10-106">Instead, you configure Exchange In-Place Hold policies to support archiving for users homed on Exchange, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="33f10-107">設定與 Exchange storage 的整合之前，請先閱讀封存中的封存以進行 [商務用 Skype Server](../../plan-your-deployment/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="33f10-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="33f10-108">如需 Exchange In-Place 保留原則的詳細資訊，請參閱 Exchange 產品檔。</span><span class="sxs-lookup"><span data-stu-id="33f10-108">For details about Exchange In-Place Hold policies, see the Exchange product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="33f10-109">設定與 Microsoft Exchange storage 的整合</span><span class="sxs-lookup"><span data-stu-id="33f10-109">Configure integration with Microsoft Exchange storage</span></span>

1. <span data-ttu-id="33f10-110">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="33f10-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="33f10-111">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="33f10-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="33f10-112">在左導覽列中 **，按一下 [\*\*\*\*監視與** 封存]，然後按一下 [封存設定]。</span><span class="sxs-lookup"><span data-stu-id="33f10-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="33f10-113">按一下封存組態清單中適當的全域、網站或集區組態名稱，再依序按一下 [編輯] 和 [顯示詳細資料]，然後執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="33f10-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="33f10-114">若要啟用與 Exchange 存放區的整合，請選取 [ **Microsoft Exchange 整合** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="33f10-114">To enable integration with Exchange storage, select the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="33f10-115">若要停用 Exchange 存放區的整合，請清除 [ **Microsoft Exchange 整合** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="33f10-115">To disable integration with Exchange storage, clear the **Microsoft Exchange integration** check box.</span></span>
    
5. <span data-ttu-id="33f10-116">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="33f10-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="33f10-117">在不同樹系中部署商務用 Skype Server 和 Microsoft Exchange 時</span><span class="sxs-lookup"><span data-stu-id="33f10-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="33f10-118">如果您使用 Microsoft Exchange 整合，而且 Microsoft Exchange Server 與商務用 Skype Server 不在相同樹系中，您必須確定下列 Exchange Active Directory 屬性已同步處理至部署商務用 Skype 伺服器的樹系：</span><span class="sxs-lookup"><span data-stu-id="33f10-118">If you use Microsoft Exchange integration and Microsoft Exchange Server is not deployed in the same forest as Skype for Business Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Skype for Business Server is deployed:</span></span>
  
- <span data-ttu-id="33f10-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="33f10-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="33f10-120">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="33f10-120">proxyAddresses</span></span>
    
<span data-ttu-id="33f10-p102">此為多重值屬性。在同步處理此屬性之時，您必須將數值合併，不要予以取代，以便確保現有數值不會遺失。</span><span class="sxs-lookup"><span data-stu-id="33f10-p102">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  

