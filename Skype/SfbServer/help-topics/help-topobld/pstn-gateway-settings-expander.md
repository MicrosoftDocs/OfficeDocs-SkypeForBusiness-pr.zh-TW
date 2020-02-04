---
title: PSTN 閘道設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
description: 若要編輯或修改公用交換電話網路 (PSTN) 閘道的設定，請修改下列欄位：
ms.openlocfilehash: b083fa22d84cdd6adf8a9636a522c5c34a732ee3
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684456"
---
# <a name="pstn-gateway-settings-expander"></a><span data-ttu-id="fcd39-103">PSTN 閘道設定展開工具</span><span class="sxs-lookup"><span data-stu-id="fcd39-103">PSTN Gateway Settings Expander</span></span>
 
<span data-ttu-id="fcd39-104">若要編輯或修改公用交換電話網路 (PSTN) 閘道的設定，請修改下列欄位：</span><span class="sxs-lookup"><span data-stu-id="fcd39-104">To edit or modify the settings for a public switched telephone network (PSTN) gateway, modify the following fields:</span></span>
  
<span data-ttu-id="fcd39-105">閘道 FQDN 或 IP 位址是必要的項目，並定義 PSTN 閘道的 [完整網域名稱 (FQDN)]\*\*\*\* 是依網域名稱系統 (DNS) 主機 (A) 記錄、靜態 HOSTS 檔案項目，或 PSTN 閘道的 IP 位址來定義。</span><span class="sxs-lookup"><span data-stu-id="fcd39-105">Gateway FQDN or IP Address is a required entry and defines wither the **Fully qualified domain name (FQDN)** of the PSTN gateway as defined by a Domain Name System (DNS) host (A) record, a static HOSTS file entry, or by the IP address of the PSTN gateway.</span></span>
  
<span data-ttu-id="fcd39-p101">[SIP 傳輸通訊協定] 可以是傳輸控制通訊協定 (TCP) 或傳輸層安全性 (TLS)。TLS 是預設值。請參閱閘道廠商文件，以了解您的閘道支援的值。預設值是 TLS，如果閘道支援 TLS 的話，應考慮使用此值作為較安全的選項。</span><span class="sxs-lookup"><span data-stu-id="fcd39-p101">The SIP Transport Protocol can either be Transmission Control Protocol (TCP) or Transport Layer Security (TLS). TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>
  
<span data-ttu-id="fcd39-110">選取是否針對閘道啟用 IPv4 和 IPv6。</span><span class="sxs-lookup"><span data-stu-id="fcd39-110">Select whether to enable IPv4 and IPv6 for the gateway.</span></span>
  
<span data-ttu-id="fcd39-111">**備用媒體 IP 位址**是對中繼伺服器的定義，其已部署的 PSTN 閘道與預設設定的 ip 位址（通常專用於 SIP 流量）不同。</span><span class="sxs-lookup"><span data-stu-id="fcd39-111">The **Alternate media IP address** is a definition for the Mediation Server for which the deployed PSTN gateway has a different IP address for media traffic than the default configured IP address, which is typically dedicated for SIP traffic.</span></span> <span data-ttu-id="fcd39-112">如果您定義此參數，則 PSTN 閘道支援針對媒體使用不同的網路介面或路徑。</span><span class="sxs-lookup"><span data-stu-id="fcd39-112">If you define this parameter, then the PSTN gateway supports a different supports a different network interface or path for media.</span></span> <span data-ttu-id="fcd39-113">如果此位址保留空白，則 PSTN 閘道不支援針對媒體使用替代路徑。</span><span class="sxs-lookup"><span data-stu-id="fcd39-113">If this address is left blank, then the PSTN gateway does not support the alternate path for media.</span></span>
  

