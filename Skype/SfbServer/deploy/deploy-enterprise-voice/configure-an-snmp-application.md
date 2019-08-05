---
title: 在商務用 Skype Server 中設定 SNMP 應用程式
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
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: 在商務用 Skype Server Enterprise Voice 中, 將 SNMP 應用程式設定為使用 E9-1-1。
ms.openlocfilehash: 575c982dae20ed085e49690edfbb141786390516
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193544"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a><span data-ttu-id="b92e9-103">在商務用 Skype Server 中設定 SNMP 應用程式</span><span class="sxs-lookup"><span data-stu-id="b92e9-103">Configure an SNMP application in Skype for Business Server</span></span>
 
<span data-ttu-id="b92e9-104">在商務用 Skype Server Enterprise Voice 中, 將 SNMP 應用程式設定為使用 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="b92e9-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="b92e9-105">商務用 Skype 伺服器包含標準的 web 服務介面, 您可以用來將位置資訊服務連線至與埠和交換器資訊相符的 MAC 位址的簡單網路管理通訊協定 (SNMP) 應用程式。</span><span class="sxs-lookup"><span data-stu-id="b92e9-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="b92e9-106">如果已安裝 SNMP 應用程式, 且位置資訊服務無法在位置資料庫中找到相符的專案, 位置資訊服務會使用用戶端提供的 MAC 位址來自動查詢應用程式。</span><span class="sxs-lookup"><span data-stu-id="b92e9-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="b92e9-107">然後, 位置資訊服務會使用 SNMP 應用程式傳回的埠和切換資訊來重新查詢位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="b92e9-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b92e9-108">MAC 位址無法在執行 Windows 8 的電腦上使用。</span><span class="sxs-lookup"><span data-stu-id="b92e9-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="b92e9-109">若要設定 SNMP 應用程式 URL</span><span class="sxs-lookup"><span data-stu-id="b92e9-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="b92e9-110">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="b92e9-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="b92e9-111">執行下列 Cmdlet 來設定 SNMP 應用程式的 URL。</span><span class="sxs-lookup"><span data-stu-id="b92e9-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="b92e9-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b92e9-112">See also</span></span>

[<span data-ttu-id="b92e9-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="b92e9-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

