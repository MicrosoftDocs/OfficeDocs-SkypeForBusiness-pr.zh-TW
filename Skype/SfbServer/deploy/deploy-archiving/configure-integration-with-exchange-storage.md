---
title: 針對商務用 Skype Server 設定與 Exchange storage 整合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: '摘要: 請閱讀本主題, 以瞭解如何在商務用 Skype Server 中設定與 Exchange 儲存體的整合。'
ms.openlocfilehash: b58aa090e4e6c51beb1f99ba5dc9020e029c8c39
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190501"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a><span data-ttu-id="8906d-103">針對商務用 Skype Server 設定與 Exchange storage 整合</span><span class="sxs-lookup"><span data-stu-id="8906d-103">Configure integration with Exchange storage for Skype for Business Server</span></span>
 
<span data-ttu-id="8906d-104">**摘要:** 請閱讀本主題, 以瞭解如何在商務用 Skype Server 中設定與 Exchange 儲存體的整合。</span><span class="sxs-lookup"><span data-stu-id="8906d-104">**Summary:** Read this topic to learn how to configure integration with Exchange storage in Skype for Business Server.</span></span>
  
<span data-ttu-id="8906d-105">如果您針對部署中的所有使用者使用 Microsoft Exchange 整合, 就不需要針對使用者設定商務用 Skype Server 封存原則。</span><span class="sxs-lookup"><span data-stu-id="8906d-105">If you use Microsoft Exchange integration for all users in your deployment, you don't need to configure Skype for Business Server archiving policies for your users.</span></span> <span data-ttu-id="8906d-106">相反地, 您可以設定 Exchange 就地保留原則, 以支援駐留在 Exchange 的使用者的封存, 且其信箱會放入就地保留。</span><span class="sxs-lookup"><span data-stu-id="8906d-106">Instead, you configure Exchange In-Place Hold policies to support archiving for users homed on Exchange, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="8906d-107">在您設定與 Exchange 儲存體的整合之前, 請先閱讀[商務用 Skype Server 中的封存方案](../../plan-your-deployment/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="8906d-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="8906d-108">如需 Exchange 就地保留原則的詳細資訊, 請參閱 Exchange 產品檔。</span><span class="sxs-lookup"><span data-stu-id="8906d-108">For details about Exchange In-Place Hold policies, see the Exchange product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="8906d-109">設定與 Microsoft Exchange 儲存空間的整合</span><span class="sxs-lookup"><span data-stu-id="8906d-109">Configure integration with Microsoft Exchange storage</span></span>

1. <span data-ttu-id="8906d-110">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="8906d-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8906d-111">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="8906d-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="8906d-112">在左側導覽列中, 按一下 [**監視及**封存], 然後按一下 [封存**配置**]。</span><span class="sxs-lookup"><span data-stu-id="8906d-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="8906d-113">在歸檔設定清單中, 按一下適當的全域、網站或池設定的名稱, 按一下 [**編輯**], 按一下 [**顯示詳細資料**], 然後執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="8906d-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="8906d-114">若要啟用與 Exchange 儲存體的整合, 請選取 [ **Microsoft Exchange 整合**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8906d-114">To enable integration with Exchange storage, select the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="8906d-115">若要停用 Exchange 儲存體整合, 請清除 [ **Microsoft Exchange 整合**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8906d-115">To disable integration with Exchange storage, clear the **Microsoft Exchange integration** check box.</span></span>
    
5. <span data-ttu-id="8906d-116">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8906d-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="8906d-117">商務用 Skype Server 和 Microsoft Exchange 部署在不同的林中</span><span class="sxs-lookup"><span data-stu-id="8906d-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="8906d-118">如果您使用的是 Microsoft Exchange 整合, 而且 Microsoft Exchange Server 與商務用 Skype Server 不在同一個林中, 您必須確認下列 Exchange Active Directory 屬性已同步處理至 Skype 適用的林中已部署商務伺服器:</span><span class="sxs-lookup"><span data-stu-id="8906d-118">If you use Microsoft Exchange integration and Microsoft Exchange Server is not deployed in the same forest as Skype for Business Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Skype for Business Server is deployed:</span></span>
  
- <span data-ttu-id="8906d-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="8906d-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="8906d-120">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="8906d-120">proxyAddresses</span></span>
    
<span data-ttu-id="8906d-121">這是多重值屬性。</span><span class="sxs-lookup"><span data-stu-id="8906d-121">This is a multi-value attribute.</span></span> <span data-ttu-id="8906d-122">同步處理此屬性時, 您必須合併值, 而不要將其取代, 以確保現有值不會遺失。</span><span class="sxs-lookup"><span data-stu-id="8906d-122">When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  

