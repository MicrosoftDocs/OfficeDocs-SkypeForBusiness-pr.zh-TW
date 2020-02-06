---
title: DNS 基本概念
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 具有可提供 DNS 服務的內建軟體，因此您可能會想要查看可用的檔，例如 DNS 策略案例指南。 如果您想要的話，您可以選擇協力廠商方案。
ms.openlocfilehash: 5438ee6ccedda6e840ca706cf285af49326a3bf4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815791"
---
# <a name="dns-basics"></a>DNS 基本概念
 
Windows Server 2016 具有可提供 DNS 服務的內建軟體，因此您可能會想要查看可用的檔，例如[DNS 策略案例指南](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide)。 如果您想要的話，您可以選擇協力廠商方案。
  
我們建議您最好的做法是，在您的部署中專門指定特定伺服器來提供 DNS。 您可能會將它設定為專用於其中一個商務用 Skype 伺服器角色的其中一個伺服器，但如果該伺服器也是某個擁有者的一部分，且事故中的商務用 Skype 已解除授權，直到重新建立 DNS 服務為止。
  
## <a name="dns-records"></a>DNS 記錄

每個名稱對應至 IP 位址（且可能是 IPv4 或 IPv6 位址），都儲存在 DNS 伺服器上的 DNS 記錄中。 此名稱在 DNS 報告中描述為 FQDN （完整功能變數名稱）。 雖然*contoso.com*是有效的* \** 功能變數名稱，但它是 contoso.com 的簡寫，所以它不明確，而且可能會參照網域中的任何伺服器。 在網域中，會參照單一伺服器的 FQDN 範例可能會**meeting01.contoso.com**。
  
> [!IMPORTANT]
> 根據預設，未加入網域之電腦的電腦名稱稱是主機名稱，而不是完全限定的功能變數名稱（FQDN）。 拓撲建造器使用 Fqdn，而不是主機名稱。 因此，您必須在要部署為邊緣伺服器且未加入網域的電腦名稱稱上設定 DNS 尾碼。 將 Fqdn 指派給執行商務用 Skype Server 的伺服器時，**只能使用標準字元**（包括 a-z、a-z、0-9 和連字號）。 請勿使用 Unicode 字元或底線。 外部 DNS 和公用 Ca 通常不支援 FQDN 中的非標準字元（也就是當 FQDN 必須指派給憑證中的 SN）時。
  
除了 IP 位址之外，FQDN 可以對應至**VIP** （虛擬 IP 位址）。 VIP 是不對應至實際物理網路介面的 IP 位址。 VIP 通常指向執行伺服器角色的伺服器池，或針對為冗余和容錯所設定的一組伺服器。
  
DNS 記錄有數種類型，與此討論最相關的記錄類型如下： 
  
- **A** ：地址記錄或主機記錄，會傳回32位的 IPv4 位址。 最常見的用途是將主機名稱對應到主機的 IP 位址。
    
- **AAAA** -IPv6 地址記錄。 傳回128位 IPv6 位址。 最常見的用途是將主機名稱對應到主機的 IP 位址。
    
- **CNAME** -標準名稱記錄。 這會將一個名稱解析為另一個名稱： DNS 查閱會使用新名稱來重試查閱。
    
- **SRV** ：服務記錄（srv 記錄）指定服務（伺服器上的進程），可在特定埠和 IP 組合中存取。 需要修正服務記錄的服務名稱，而且不能在您的 SIP 網域中進行自訂。 有些使用者服務會使用簡單的 Url。 SRV 記錄必須指向同一個 SIP 網域中的位置，所以如果您有多個網域，則特定的服務會需要多個 SRV 記錄。
    
## <a name="how-to-choose-a-sip-domain-name"></a>如何選擇 SIP 功能變數名稱
<a name="BK_NameSIP"> </a>

組織的 SIP 功能變數名稱通常會與使用者所提供的電子郵件地址相符。 如果貴組織中的使用者會擁有電子郵件地址（例如 Brown@contoso.com）， \<則只有 contoso.com\>才能擁有 contoso.com 功能變數名稱的組織的首選 sip-網域。
  
### <a name="multiple-sip-domains"></a>多個 SIP 網域

 在某些情況下，您的組織可能需要幾個 SIP 網域。 舉例來說，如果 Fabrikam.com 是由 contoso.com 取得，您可能需要建立新的 SIP 網域，讓商務用 Skype 伺服器辨識並接受連線。 當您這麼做時，您必須建立一組使用 contoso.com 的所有 DNS 記錄，並在新的 Fqdn 中顯示在何處傳送 Fabrikam 的要求。
  
## <a name="dns-load-balancing"></a>DNS 負載平衡
<a name="BK_NameSIP"> </a>

您可以在設定為伺服器池中的數個伺服器之間，使用 DNS 來共用流量負載。 若要這樣做，您可以為池的 FQDN 建立數個記錄，每個記錄都指向池中節點的 IP 位址。
  
若要進一步討論負載平衡，請參閱[DNS 負載平衡](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)。
  

