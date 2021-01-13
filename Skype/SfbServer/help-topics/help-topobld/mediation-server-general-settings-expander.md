---
title: 中繼伺服器一般設定展開工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/14/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: a00573b06c1900718fd670c96a21ffab069b491e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806723"
---
# <a name="mediation-server-general-settings-expander"></a><span data-ttu-id="341a4-102">中繼伺服器一般設定展開工具</span><span class="sxs-lookup"><span data-stu-id="341a4-102">Mediation Server General Settings Expander</span></span>
 


## <a name="general-settings"></a><span data-ttu-id="341a4-103">一般設定</span><span class="sxs-lookup"><span data-stu-id="341a4-103">General settings</span></span>

<span data-ttu-id="341a4-p101">中繼伺服器集區或中繼伺服器的完整網域名稱 (FQDN)。編輯伺服器的 FQDN 會變更此值。您必須有符合新值的網域名稱系統 (DNS) 主機 (A) 記錄。</span><span class="sxs-lookup"><span data-stu-id="341a4-p101">Fully qualified domain name (FQDN) of the Mediation Server pool or Mediation Server. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="341a4-107">在 [關聯] 區段中，選取要與中繼伺服器集區或中繼伺服器關聯的 Edge Server 或 Edge Server 集區。</span><span class="sxs-lookup"><span data-stu-id="341a4-107">In the **Associations** section, you select an Edge Server or Edge Server pool to associate with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="341a4-108">您選取的邊界是轉送伺服器的媒體元件將用於外部使用者 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="341a4-108">You select the Edge that the Mediation Server's media components will use for External user Enterprise Voice.</span></span>
  
<span data-ttu-id="341a4-109">如果您目前並未定義 Edge Server，而需要將中繼伺服器與 Edge Server 關聯，請按一下 [新增] 並在 [定義新的 Edge 集區精靈] 中定義新的 Edge Server 或 Edge Server 集區。</span><span class="sxs-lookup"><span data-stu-id="341a4-109">If you do not have an Edge Server currently defined and need to associate the Mediation Server with an Edge Server, click **New** and define the new Edge Server or Edge Server pool in the Define the New Edge pool wizard.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="341a4-110">下一個躍點設定</span><span class="sxs-lookup"><span data-stu-id="341a4-110">Next hop settings</span></span>

<span data-ttu-id="341a4-111">您可以從下拉式清單中選取定義的 Enterprise Edition 前端集區或 Standard Edition 前端伺服器，指定中繼伺服器集區或中繼伺服器的下一個躍點。</span><span class="sxs-lookup"><span data-stu-id="341a4-111">You specify the Mediation Server pool or Mediation Server next hop by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="341a4-112">Director 或 Director 集區不是中繼伺服器集區或中繼伺服器下一個躍點的有效選項，亦不會顯示在清單中。</span><span class="sxs-lookup"><span data-stu-id="341a4-112">A Director or Director pool is not a valid selection for a Mediation Server pool or Mediation Server next hop, and will not appear in the list.</span></span> <span data-ttu-id="341a4-113">按一下 **[確定]** 以接受並儲存變更。</span><span class="sxs-lookup"><span data-stu-id="341a4-113">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="341a4-114">按一下 [取消] 捨棄變更並結束內容頁面。</span><span class="sxs-lookup"><span data-stu-id="341a4-114">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  
## <a name="pstn-gateway-settings"></a><span data-ttu-id="341a4-115">PSTN 閘道設定</span><span class="sxs-lookup"><span data-stu-id="341a4-115">PSTN gateway settings</span></span>

1. <span data-ttu-id="341a4-p104">您將定義與中繼伺服器集區或中繼伺服器關聯的 PSTN 閘道。如果已經定義閘道，可以將其用來與中繼伺服器相關聯。如果您啟用中繼伺服器的組合，便會在集區伺服器上針對傳輸層安全性 (TLS) 定義聆聽連接埠範圍。此連接埠預設為 5067。如果您選取 [啟用 TCP 連接埠]，則必須為組合的中繼伺服器定義傳輸控制通訊協定 (TCP) 連接埠。這是選用的設定，您應該參考閘道或 PSTN 需求，來決定是否需要這項設定。TCP 連接埠值預設為 5068。</span><span class="sxs-lookup"><span data-stu-id="341a4-p104">You define PSTN gateways that are associated with the Mediation Server pool or Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server. If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>
    
2. <span data-ttu-id="341a4-p105">與組合中繼伺服器相關聯的主幹。如果已經定義主幹，可以將其用來與中繼伺服器相關聯。</span><span class="sxs-lookup"><span data-stu-id="341a4-p105">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
3. <span data-ttu-id="341a4-p106">如果您有多個主幹與中繼伺服器相關聯，您可以選取主幹，然後按一下 [成為預設] 指定預設主幹。若要取消選取成為預設的閘道，請按一下 [取消預設]。</span><span class="sxs-lookup"><span data-stu-id="341a4-p106">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the trunk and then clicking **Make Default**. To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    

