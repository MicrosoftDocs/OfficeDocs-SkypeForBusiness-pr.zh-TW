---
title: 中繼伺服器一般設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/14/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: a460cfcaf696740fa108be451156d53bec96f95d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696998"
---
# <a name="mediation-server-general-settings-expander"></a><span data-ttu-id="37797-102">中繼伺服器一般設定展開工具</span><span class="sxs-lookup"><span data-stu-id="37797-102">Mediation Server General Settings Expander</span></span>
 


## <a name="general-settings"></a><span data-ttu-id="37797-103">一般設定</span><span class="sxs-lookup"><span data-stu-id="37797-103">General settings</span></span>

<span data-ttu-id="37797-104">中繼伺服器池或中繼伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="37797-104">Fully qualified domain name (FQDN) of the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="37797-105">編輯伺服器的 FQDN 會變更此值。</span><span class="sxs-lookup"><span data-stu-id="37797-105">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="37797-106">您必須有符合新值的網域名稱系統 (DNS) 主機 (A) 記錄。</span><span class="sxs-lookup"><span data-stu-id="37797-106">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="37797-107">在 [**關聯**性] 區段中，選取 [邊緣伺服器] 或 [edge 伺服器] 池，以與中繼伺服器池或轉送伺服器伺服器建立關聯。</span><span class="sxs-lookup"><span data-stu-id="37797-107">In the **Associations** section, you select an Edge Server or Edge Server pool to associate with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="37797-108">您選取轉送伺服器媒體元件將用於外部使用者企業語音的邊緣。</span><span class="sxs-lookup"><span data-stu-id="37797-108">You select the Edge that the Mediation Server's media components will use for External user Enterprise Voice.</span></span>
  
<span data-ttu-id="37797-109">如果您目前未定義 Edge 伺服器，且需要將中繼伺服器與 Edge 伺服器關聯，請按一下 [**新增**]，然後在 [定義新的邊緣池] 嚮導中定義新的 edge 伺服器或 edge 伺服器池。</span><span class="sxs-lookup"><span data-stu-id="37797-109">If you do not have an Edge Server currently defined and need to associate the Mediation Server with an Edge Server, click **New** and define the new Edge Server or Edge Server pool in the Define the New Edge pool wizard.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="37797-110">下一個躍點設定</span><span class="sxs-lookup"><span data-stu-id="37797-110">Next hop settings</span></span>

<span data-ttu-id="37797-111">您可以從下拉式清單中選取已定義的企業版前端池或標準版前端伺服器，以指定中繼伺服器池或中繼伺服器的下一個躍點。</span><span class="sxs-lookup"><span data-stu-id="37797-111">You specify the Mediation Server pool or Mediation Server next hop by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="37797-112">主管或主管池不是中繼伺服器池或中繼伺服器下一個躍點的有效選取範圍，且不會出現在清單中。</span><span class="sxs-lookup"><span data-stu-id="37797-112">A Director or Director pool is not a valid selection for a Mediation Server pool or Mediation Server next hop, and will not appear in the list.</span></span> <span data-ttu-id="37797-113">按一下 **[確定]** 接受並儲存您的變更。</span><span class="sxs-lookup"><span data-stu-id="37797-113">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="37797-114">按一下 [取消]\*\*\*\* 捨棄變更並結束內容頁面。</span><span class="sxs-lookup"><span data-stu-id="37797-114">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  
## <a name="pstn-gateway-settings"></a><span data-ttu-id="37797-115">PSTN 閘道設定</span><span class="sxs-lookup"><span data-stu-id="37797-115">PSTN gateway settings</span></span>

1. <span data-ttu-id="37797-116">您定義與中繼伺服器池或轉送伺服器伺服器相關聯的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="37797-116">You define PSTN gateways that are associated with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="37797-117">如果您已定義閘道，就可以將它們與中繼伺服器建立關聯。</span><span class="sxs-lookup"><span data-stu-id="37797-117">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span> <span data-ttu-id="37797-118">如果您啟用中繼伺服器的組合，便會在集區伺服器上針對傳輸層安全性 (TLS) 定義聆聽連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="37797-118">If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS).</span></span> <span data-ttu-id="37797-119">此連接埠預設為 5067。</span><span class="sxs-lookup"><span data-stu-id="37797-119">By default, this port is 5067.</span></span> <span data-ttu-id="37797-120">如果您選取 [啟用 TCP 連接埠]\*\*\*\*，則必須為組合的中繼伺服器定義傳輸控制通訊協定 (TCP) 連接埠。</span><span class="sxs-lookup"><span data-stu-id="37797-120">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="37797-121">這是選用的設定，您應該參考閘道或 PSTN 需求，來決定是否需要這項設定。</span><span class="sxs-lookup"><span data-stu-id="37797-121">This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this.</span></span> <span data-ttu-id="37797-122">TCP 連接埠值預設為 5068。</span><span class="sxs-lookup"><span data-stu-id="37797-122">By default, the TCP port value is 5068.</span></span>
    
2. <span data-ttu-id="37797-p105">與組合中繼伺服器相關聯的主幹。如果已經定義主幹，可以將其用來與中繼伺服器相關聯。</span><span class="sxs-lookup"><span data-stu-id="37797-p105">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
3. <span data-ttu-id="37797-125">如果您有多個與中繼伺服器相關聯的幹線，您可以選取主幹，然後按一下 [**設為預設值**] 來指定預設幹線。</span><span class="sxs-lookup"><span data-stu-id="37797-125">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the trunk and then clicking **Make Default**.</span></span> <span data-ttu-id="37797-126">若要取消選取成為預設的閘道，請按一下 [取消預設]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="37797-126">To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    

