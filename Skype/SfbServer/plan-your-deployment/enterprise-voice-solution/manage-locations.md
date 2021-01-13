---
title: 在商務用 Skype Server 中管理 SIP 主幹服務提供者的位置
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: 在商務用 Skype Server Enterprise Voice 中，針對使用 SIP 主幹提供者的 E9-1-1 部署規劃位置資訊資料庫或類似外部資料庫所需的決策。
ms.openlocfilehash: 9918fc2cb6bc9d05166d648ab3285a964d15f290
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825433"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a><span data-ttu-id="79e10-103">在商務用 Skype Server 中管理 SIP 主幹服務提供者的位置</span><span class="sxs-lookup"><span data-stu-id="79e10-103">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>

<span data-ttu-id="79e10-104">在商務用 Skype Server Enterprise Voice 中，針對使用 SIP 主幹提供者的 E9-1-1 部署規劃位置資訊資料庫或類似外部資料庫所需的決策。</span><span class="sxs-lookup"><span data-stu-id="79e10-104">Decisions necessary for planning an the location information database, or a similar external database, for an E9-1-1 deployment using SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="79e10-105">若要將商務用 Skype 伺服器設定為自動在網路中尋找用戶端，您必須使用網路線路圖填滿位置資訊服務資料庫，併發布位置，或連結至已經包含正確對應的外部資料庫。</span><span class="sxs-lookup"><span data-stu-id="79e10-105">To configure Skype for Business Server to automatically locate clients within a network, you need to either populate the Location Information service database with a network wiremap and publish the locations, or link to an external database that already contains the correct mappings.</span></span> <span data-ttu-id="79e10-106">在此程式中，您必須使用 E9-1-1 服務提供者驗證位置的市政位址。</span><span class="sxs-lookup"><span data-stu-id="79e10-106">As part of this process, you need to validate the civic addresses of the locations with your E9-1-1 service provider.</span></span> <span data-ttu-id="79e10-107">如需詳細資訊，請參閱部署檔中 [的 Configure Location 資料庫](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="79e10-107">For details, see [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in the Deployment documentation.</span></span>

<span data-ttu-id="79e10-108">您可以使用 ERL) （包含市政位址及大樓內的特定位址） (的 [緊急回應] 位置，填入位置資訊服務資料庫。</span><span class="sxs-lookup"><span data-stu-id="79e10-108">You populate the Location Information service database with an Emergency Response Location (ERL), which consists of a civic address and the specific address within a building.</span></span> <span data-ttu-id="79e10-109">位置資訊服務 **位置** 欄位是大樓內的特定位置，其最大長度為20個字元 (包含空格) 。</span><span class="sxs-lookup"><span data-stu-id="79e10-109">The Location Information service **Location** field, which is the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="79e10-110">在此有限長度內，嘗試包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="79e10-110">Within that limited length, try to include the following:</span></span>

- <span data-ttu-id="79e10-111">易於辨識的名稱，可識別911呼叫者的位置，以協助確保緊急回應程式在到達市政位址時立即找到特定位置。</span><span class="sxs-lookup"><span data-stu-id="79e10-111">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address.</span></span> <span data-ttu-id="79e10-112">此位置名稱可以包含大樓編號、底價編號、翼標示符、會議室編號等等。</span><span class="sxs-lookup"><span data-stu-id="79e10-112">This location name may include a building number, floor number, wing designator, room number, and so on.</span></span> <span data-ttu-id="79e10-113">避免只有員工知道的昵稱，這可能會造成緊急回應程式進入錯誤的位置。</span><span class="sxs-lookup"><span data-stu-id="79e10-113">Avoid nicknames known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

- <span data-ttu-id="79e10-114">一個位置識別碼，可協助使用者輕鬆查看其商務用 Skype 用戶端是否已挑選正確的位置。</span><span class="sxs-lookup"><span data-stu-id="79e10-114">A location identifier that helps users to easily see that their Skype for Business client picked up the correct location.</span></span> <span data-ttu-id="79e10-115">商務用 Skype 用戶端會自動連接並顯示其頁首中已探索的 **位置** 和 **城市** 欄位。</span><span class="sxs-lookup"><span data-stu-id="79e10-115">The Skype for Business client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="79e10-116">最佳作法是將大樓的街道位址新增至每個位置識別碼 (例如，"第一層 <street number> " ) 。</span><span class="sxs-lookup"><span data-stu-id="79e10-116">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor <street number>").</span></span> <span data-ttu-id="79e10-117">沒有街道位址，「第一層」等一般位置識別碼可以套用到城市中的任何辦公樓。</span><span class="sxs-lookup"><span data-stu-id="79e10-117">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

- <span data-ttu-id="79e10-118">如果該位置是由無線存取點所決定，您可以新增 **[near]** (例如，「接近第一層1234」 ) 。</span><span class="sxs-lookup"><span data-stu-id="79e10-118">If the location is approximate because it's determined by a wireless access point, you can add the word **[Near]** (for example, "Near 1st Floor 1234").</span></span>

> [!NOTE]
> <span data-ttu-id="79e10-119">在使用商務用 Skype Server 管理命令介面命令來發佈至中央位置資料庫時，這些位置會無法供用戶端使用，而且會複製到集區的本機存放區。</span><span class="sxs-lookup"><span data-stu-id="79e10-119">Locations added to the central location database are not available to the client until they are published by using a Skype for Business Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="79e10-120">如需詳細資訊，請參閱部署檔中 [的發佈位置資料庫](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="79e10-120">For details, see [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) in the Deployment documentation.</span></span>

<span data-ttu-id="79e10-121">下列各節討論在填充及維護位置資料庫時，需要考慮的考慮事項。</span><span class="sxs-lookup"><span data-stu-id="79e10-121">The following sections discuss considerations that you need to take into account when populating and maintaining the location database.</span></span>

## <a name="populating-the-location-database"></a><span data-ttu-id="79e10-122">填充位置資料庫</span><span class="sxs-lookup"><span data-stu-id="79e10-122">Populating the Location Database</span></span>

<span data-ttu-id="79e10-123">下列問題可協助您決定如何填入位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="79e10-123">The following questions can help you determine how to populate the location database.</span></span>

 <span data-ttu-id="79e10-124">**您將使用哪個程式填入位置資料庫？**</span><span class="sxs-lookup"><span data-stu-id="79e10-124">**What process will you use to populate the location database?**</span></span>

<span data-ttu-id="79e10-125">資料存在的位置，以及您需要採取哪些步驟將資料轉換成位置資料庫所需的格式？</span><span class="sxs-lookup"><span data-stu-id="79e10-125">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database?</span></span> <span data-ttu-id="79e10-126">是否要使用 CSV 檔案個別新增位置，還是大量使用 CSV 檔案？</span><span class="sxs-lookup"><span data-stu-id="79e10-126">Will you add locations individually, or in bulk, by using a CSV file?</span></span>

 <span data-ttu-id="79e10-127">**您是否有已包含位置對應的協力廠商資料庫？**</span><span class="sxs-lookup"><span data-stu-id="79e10-127">**Do you have a third party database that already contains a mapping of locations?**</span></span>

<span data-ttu-id="79e10-128">使用 [次要位置資訊服務] 選項來連線至協力廠商資料庫，您可以使用離線平臺來分組和管理位置。</span><span class="sxs-lookup"><span data-stu-id="79e10-128">By using the Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="79e10-129">這種方法的好處是，除了將位置與網路識別碼相關聯之外，也可以將位置與使用者產生關聯。</span><span class="sxs-lookup"><span data-stu-id="79e10-129">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="79e10-130">這表示位置資訊服務可以傳回多個來自次要位置資訊服務的位址到商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="79e10-130">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Skype for Business client.</span></span> <span data-ttu-id="79e10-131">然後，使用者可以選擇最適合的位置。</span><span class="sxs-lookup"><span data-stu-id="79e10-131">The user can then choose the most appropriate location.</span></span>

<span data-ttu-id="79e10-132">若要與位置資訊服務整合，協力廠商資料庫必須遵循 Lync Server 位置要求/回應架構。</span><span class="sxs-lookup"><span data-stu-id="79e10-132">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="79e10-133">如需詳細資訊，請參閱  [[E911WS]： E911 支援通訊協定規格的 Web 服務]](https://go.microsoft.com/fwlink/p/?linkid=213819)。</span><span class="sxs-lookup"><span data-stu-id="79e10-133">For details, see  ["[MS-E911WS]: Web Service for E911 Support Protocol Specification"](https://go.microsoft.com/fwlink/p/?linkid=213819).</span></span> <span data-ttu-id="79e10-134">如需部署次要位置資訊服務的詳細資訊，請參閱部署檔中的 [在商務用 Skype Server 中設定次要位置資訊服務](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) 。</span><span class="sxs-lookup"><span data-stu-id="79e10-134">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="79e10-135">如需有關填充位置資料庫的詳細資訊，請參閱部署檔中 [的 Configure Location 資料庫](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="79e10-135">For details about populating the location database, see [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in the Deployment documentation.</span></span>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="79e10-136">維護位置資料庫</span><span class="sxs-lookup"><span data-stu-id="79e10-136">Maintaining the Location Database</span></span>

<span data-ttu-id="79e10-137">填滿位置資料庫之後，您需要開發一個策略，以在網路設定變更時更新資料庫。</span><span class="sxs-lookup"><span data-stu-id="79e10-137">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes.</span></span> <span data-ttu-id="79e10-138">下列問題可協助您決定如何維護位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="79e10-138">The following questions will help you determine how to maintain the location database.</span></span>

 <span data-ttu-id="79e10-139">**您將如何更新位置資料庫？**</span><span class="sxs-lookup"><span data-stu-id="79e10-139">**How will you update the location database?**</span></span>

<span data-ttu-id="79e10-140">有幾個案例需要更新位置資料庫，包括新增 Wap、office recabling (產生不同的切換指派) 及子網擴充。</span><span class="sxs-lookup"><span data-stu-id="79e10-140">There are several scenarios that require an update to the location database, including adding WAPs, office recabling (resulting in different switch assignments), and subnet expansion.</span></span> <span data-ttu-id="79e10-141">您是否會直接更新每個個別位置，或是使用 CSV 檔案執行所有位置的大量更新？</span><span class="sxs-lookup"><span data-stu-id="79e10-141">Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

 <span data-ttu-id="79e10-142">**您是否會使用 SNMP 應用程式，將 Lync 用戶端 MAC 位址與埠及切換識別碼對應？**</span><span class="sxs-lookup"><span data-stu-id="79e10-142">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>

<span data-ttu-id="79e10-143">如果您使用 SNMP 應用程式，則必須開發手動程式，以在 SNMP 應用程式和位置資料庫之間保持切換底盤及埠資訊的一致性。</span><span class="sxs-lookup"><span data-stu-id="79e10-143">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="79e10-144">如果 SNMP 應用程式傳回資料庫中未包含的主機殼 IP 位址或埠識別碼，則位置資訊服務將無法傳回用戶端的位置。</span><span class="sxs-lookup"><span data-stu-id="79e10-144">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>


