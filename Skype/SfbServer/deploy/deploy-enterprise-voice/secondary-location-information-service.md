---
title: 在商務用 Skype Server 中設定次要位置資訊服務
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: 為商務用 Skype Server Enterprise Voice 中的 E9-1-1，設定次要位置來源 (SLS) 資料庫。
ms.openlocfilehash: fd70957526d193951b56211c0d5a6623a26419e2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830643"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="fb7af-103">在商務用 Skype Server 中設定次要位置資訊服務</span><span class="sxs-lookup"><span data-stu-id="fb7af-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="fb7af-104">為商務用 Skype Server Enterprise Voice 中的 E9-1-1，設定次要位置來源 (SLS) 資料庫。</span><span class="sxs-lookup"><span data-stu-id="fb7af-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="fb7af-105">商務用 Skype 伺服器提供 web 服務介面，您可以用來將位置資訊服務指向次要位置來源 (SLS) 資料庫。</span><span class="sxs-lookup"><span data-stu-id="fb7af-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="fb7af-106">連接至 SLS 資料庫的 web 服務介面必須符合位置資訊服務 WSDL。</span><span class="sxs-lookup"><span data-stu-id="fb7af-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="fb7af-107">如果已設定位置資料庫和次要位置資料庫，則位置資訊服務會先查詢位置資料庫，如果找不到相符的位置，就會將位置要求從用戶端傳送至 SLS 資料庫。</span><span class="sxs-lookup"><span data-stu-id="fb7af-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="fb7af-108">如果該位置存在於 SLS 中，則位置資訊服務會將該位置傳回用戶端。</span><span class="sxs-lookup"><span data-stu-id="fb7af-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="fb7af-109">設定次要位置資料庫</span><span class="sxs-lookup"><span data-stu-id="fb7af-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="fb7af-110">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="fb7af-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="fb7af-111">執行下列 Cmdlet 以設定次要位置資料庫的位置 URL。</span><span class="sxs-lookup"><span data-stu-id="fb7af-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="fb7af-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fb7af-112">See also</span></span>

[<span data-ttu-id="fb7af-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="fb7af-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

