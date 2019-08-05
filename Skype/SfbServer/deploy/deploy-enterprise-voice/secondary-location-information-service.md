---
title: 在商務用 Skype Server 中設定次要位置資訊服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: 在商務用 Skype Server Enterprise Voice 中, 針對 E9-1-1 設定次要位置來源 (SLS) 資料庫。
ms.openlocfilehash: 0d637b8b2b61526837be2d56b8654f40bc556064
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191131"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="8fc03-103">在商務用 Skype Server 中設定次要位置資訊服務</span><span class="sxs-lookup"><span data-stu-id="8fc03-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="8fc03-104">在商務用 Skype Server Enterprise Voice 中, 針對 E9-1-1 設定次要位置來源 (SLS) 資料庫。</span><span class="sxs-lookup"><span data-stu-id="8fc03-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="8fc03-105">商務用 Skype 伺服器提供 web 服務介面, 您可以用來將位置資訊服務指向次要位置來源 (SLS) 資料庫。</span><span class="sxs-lookup"><span data-stu-id="8fc03-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="8fc03-106">連接到 SLS 資料庫的 web 服務介面必須符合位置資訊服務 WSDL。</span><span class="sxs-lookup"><span data-stu-id="8fc03-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="8fc03-107">如果已設定位置資料庫和次要位置資料庫, 位置資訊服務會先查詢位置資料庫, 如果沒有找到相符的專案, 則會將位置要求從用戶端傳送到 SLS 資料庫。</span><span class="sxs-lookup"><span data-stu-id="8fc03-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="8fc03-108">如果該位置存在於 SLS 中, 則位置資訊服務接著會將該位置傳送回用戶端。</span><span class="sxs-lookup"><span data-stu-id="8fc03-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="8fc03-109">若要設定次要位置資料庫</span><span class="sxs-lookup"><span data-stu-id="8fc03-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="8fc03-110">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="8fc03-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8fc03-111">執行下列 Cmdlet 來設定次要位置資料庫位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="8fc03-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="8fc03-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8fc03-112">See also</span></span>

[<span data-ttu-id="8fc03-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="8fc03-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

