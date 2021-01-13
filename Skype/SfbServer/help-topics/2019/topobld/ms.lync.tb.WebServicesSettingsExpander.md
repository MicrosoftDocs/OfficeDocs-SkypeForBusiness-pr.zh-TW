---
title: Web 服務設定展開工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
ROBOTS: NOINDEX, NOFOLLOW
description: 您可以從拓撲產生器內，修改用於內部和外部 web 服務的埠設定。 此外，如果您要部署網域名稱系統 (DNS) 負載平衡，您可以使用拓撲產生器，設定集區的完整功能變數名稱 (FQDN) ，以解析為該集區中所有伺服器的實體 IP 位址。
ms.openlocfilehash: 99f052ebbfc4199f077744eee444333822075c24
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800693"
---
# <a name="web-services-settings-expander"></a><span data-ttu-id="0847a-104">Web 服務設定展開工具</span><span class="sxs-lookup"><span data-stu-id="0847a-104">Web Services Settings Expander</span></span>
 
<span data-ttu-id="0847a-105">您可以從拓撲產生器內，修改用於內部和外部 web 服務的埠設定。</span><span class="sxs-lookup"><span data-stu-id="0847a-105">From within Topology Builder, you can modify the port settings used for both your internal and external web services.</span></span> <span data-ttu-id="0847a-106">此外，如果您要部署網域名稱系統 (DNS) 負載平衡，您可以使用拓撲產生器，設定集區的完整功能變數名稱 (FQDN) ，以解析為該集區中所有伺服器的實體 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0847a-106">In addition, and if you are deploying Domain Name System (DNS) load balancing, you can use Topology Builder to configure the fully qualified domain name (FQDN) of the pool that resolves to the physical IP addresses of all the servers in that pool.</span></span>
  
### <a name="editing-web-services-settings"></a><span data-ttu-id="0847a-107">編輯 Web 服務設定</span><span class="sxs-lookup"><span data-stu-id="0847a-107">Editing Web Services Settings</span></span>

1. <span data-ttu-id="0847a-108">選取適當的 Standard Edition 前端伺服器或適當的 Enterprise Edition 前端集區，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="0847a-108">Select the appropriate Standard Edition Front End Server or the appropriate Enterprise Edition Front End Pool, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="0847a-109">在 **[編輯內容]** 對話方塊中，按一下 **[Web 服務]** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="0847a-109">In the **Edit Properties** dialog box, click the **Web services** tab.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="0847a-110">如果您有一個以上的前端集區或前端伺服器，則外部 Web 服務 FQDN 必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="0847a-110">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="0847a-111">例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為 **pool01.contoso.com**，則無法將 **pool01.contoso.com** 用於另一個前端集區或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="0847a-111">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="0847a-112">如果您也要部署 Director，則為任何 Director 或 Director 集區定義的外部 Web 服務 FQDN，都必須與任何其他 Director 或 Director 集區以及任何前端集區或前端伺服器都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="0847a-112">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="0847a-113">如果您決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 必須與其他任何前端集區、Director 或 Director 集區是唯一的。</span><span class="sxs-lookup"><span data-stu-id="0847a-113">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
3. <span data-ttu-id="0847a-114">如果您要編輯的是 Enterprise Edition 集區的屬性，您可以選取 [覆 **寫 FQDN**] 選項。</span><span class="sxs-lookup"><span data-stu-id="0847a-114">If you are editing the properties of an Enterprise Edition pool, you have the option to select **Override FQDN**.</span></span> <span data-ttu-id="0847a-115">只有在您使用網域名稱系統 (DNS) 負載平衡時，才應選取此選項。</span><span class="sxs-lookup"><span data-stu-id="0847a-115">This option should be selected only if you are using Domain Name System (DNS) load balancing.</span></span> <span data-ttu-id="0847a-116">如果您使用 DNS 負載平衡，請選取 **[覆寫 FQDN]**，然後在文字方塊中輸入集區的 FQDN，以解析至該集區中所有伺服器的實體 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0847a-116">If you are using DNS load balancing, select **Override FQDN** and then, in the text box, type the FQDN of the pool that resolves to the physical IP addresses of all the servers in that pool.</span></span> <span data-ttu-id="0847a-117">如果您未使用 DNS 負載平衡，且未選取 **[覆寫 FQDN]**，則無法變更內部 Web 服務 FQDN。</span><span class="sxs-lookup"><span data-stu-id="0847a-117">If you are not using DNS load balancing, and if you do not select **Override FQDN**, you cannot change the Internal web services FQDN.</span></span> <span data-ttu-id="0847a-118">內部 web 服務 FQDN 是內部使用者用來連線至商務用 Skype 伺服器的 URL。</span><span class="sxs-lookup"><span data-stu-id="0847a-118">The Internal web services FQDN is the URL used by internal users to connect to Skype for Business Server.</span></span>
    
4. <span data-ttu-id="0847a-p105">(選用) 在 **[聆聽連接埠]** 和 **[發行的連接埠]** 中輸入新的 HTTP、HTTPS 或是 HTTP 和 HTTPS 值。聆聽連接埠是 Internet Information Services (IIS) 用來聆聽傳入工作階段初始通訊協定 (SIP) 流量的連接埠；發行的連接埠是在負載平衡器或反向 Proxy 伺服器上設定的連接埠，同樣用來聆聽傳入 SIP 流量。根據預設，HTTP 聆聽連接埠和 HTTP 發行的連接埠都設為連接埠 80；對應的 HTTPS 連接埠都設為 443。兩個 HTTP 發行的連接埠的預設值都是 8080，對應的 HTTPS 連接埠設為 4443。</span><span class="sxs-lookup"><span data-stu-id="0847a-p105">Optionally, enter new HTTP, HTTPS, or HTTP and HTTPS values for the **Listening ports** and the **Published ports**. Listening ports are the ports used by Internet Information Services (IIS) to listen for incoming Session Initiation Protocol (SIP) traffic; published ports are ports configured on a load balancer or reverse proxy server and are also used to listen for incoming SIP traffic. By default, both the HTTP listening port and the HTTP published port are set to port 80; the corresponding HTTPS ports are both set to 443. The default value for the two HTTP published ports is 8080 and the corresponding HTTPS ports are set to 4443.</span></span>
    
5. <span data-ttu-id="0847a-123">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="0847a-123">Click **OK**.</span></span>
    
<span data-ttu-id="0847a-124">如果您修改內部 FQDN 或任何聆聽埠指派，則必須在集區中的所有伺服器上重新執行本機安裝程式，這些變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="0847a-124">If you modify either the internal FQDN or any of the listening port assignments, you must local setup again on all the servers in the pool in order to have those changes take effect.</span></span>
  

