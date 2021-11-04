---
title: DNS 基本知識
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 具有可提供 DNS 服務的內建軟體，所以您可能想要查看可用的檔，例如 DNS 原則案例指南。 您可以選擇協力廠商的解決方案（如果您願意）。
ms.openlocfilehash: fe5c38aa22f87e9096d9c887c387938e1cf66ab3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765231"
---
# <a name="dns-basics"></a>DNS 基本知識
 
Windows Server 2016 具有可提供 DNS 服務的內建軟體，所以您可能想要查看可用的檔，例如[DNS 原則案例指南](/windows-server/networking/dns/deploy/dns-policy-scenario-guide)。 您可以選擇協力廠商的解決方案（如果您願意）。
  
建議的最佳作法是，在您的實施中指定特定的伺服器，以提供 DNS。 您可以在其中一個伺服器角色商務用 Skype 專用的伺服器上進行設定，但如果該伺服器也是集區的一部分，且在意外情況下解除委任，則在重新建立 DNS 服務之前商務用 Skype 會無法正常作業。
  
## <a name="dns-records"></a>DNS 記錄

名稱對應至 IP 位址的每個對應 (，也可以是 IPv4 或 IPv6 的位址) 儲存在 DNS 伺服器上的 DNS 記錄中。 在 DNS 報告中，特別是以 FQDN （即完整功能變數名稱）說明的名稱。 雖然 *contoso.com* 是有效的功能變數名稱，但它是 *\* contoso.com* 的簡寫，所以是不明確的，而且可能會參照網域中的任何伺服器。 在您的網域中，會參照單一伺服器的 FQDN 範例可能是 **meeting01.contoso.com**。
  
> [!IMPORTANT]
> 依預設，未加入網域之電腦的電腦名稱稱為主機名稱，而不是完整功能變數名稱 (FQDN) 。 拓撲產生器使用 Fqdn，而非主機名稱。 因此，在未加入網域但要部署為 Edge Server 電腦的電腦名稱中，您必須設定 DNS 尾碼。 將 fqdn 指派給執行商務用 Skype Server 的伺服器時，請 **只使用標準字元** (包括 A-Z、a-z、0-9 和連字號) 。 請勿使用 Unicode 字元或底線。 也就是當 FQDN 必須指派給憑證的 SN 時，外部 DNS 與公用 CA 通常不支援在 FQDN 中使用非標準字元。
  
除了 IP 位址，FQDN 也可以對應至 **VIP** （虛擬 IP 位址）。 VIP 是不會對應至實際實體網路介面的 IP 位址。 VIP 通常是指執行伺服器角色的伺服器集區，或是一對設定為冗余及容錯的伺服器。
  
有幾種 DNS 記錄類型，與本討論最相關的 DNS 記錄類型包括： 
  
- **A** --a address Record 或 Host record 會傳回32位 IPv4 位址。 最常用於將主機名稱對應至主機的 IP 位址。
    
- **AAAA** -a IPv6 address record。 會傳回128位 IPv6 位址。 最常用於將主機名稱對應至主機的 IP 位址。
    
- **CNAME** --正常化名稱記錄。 這會將一個名稱解析為另一個名稱： DNS 查閱會以新名稱重試查閱。
    
- **Srv** —服務記錄 (srv 記錄) 指定服務 (在特定埠和 IP 組合上存取之伺服器) 上的處理常式。 需要服務記錄的服務名稱是固定的，而且無法自訂，只是讓他們成為 SIP 網域的一部分。 部分使用者服務使用簡單 URLs。 SRV 記錄必須指向相同 SIP 網域中的位置，因此如果您有多個網域，您會需要一個指定服務的多個 SRV 記錄。
    
## <a name="how-to-choose-a-sip-domain-name"></a>如何選擇 SIP 功能變數名稱
<a name="BK_NameSIP"> </a>

組織的 SIP 功能變數名稱通常會與其使用者提供的電子郵件地址對齊。 如果您組織中的使用者會擁有類似 Brown@contoso.com 的電子郵件地址，則 \<sip-domain\> 使用 contoso.com 功能變數名稱的組織偏好只是 contoso.com。
  
### <a name="multiple-sip-domains"></a>多個 SIP 網域

 在某些情況下，您的組織可能需要數個 SIP 網域。 例如，如果 Fabrikam.com 是由 contoso.com 取得，您可能需要建立商務用 Skype Server 辨識並接受連線的新 SIP 網域。 當您執行此動作時，您必須建立所有使用 contoso.com 的 DNS 記錄的其他集合，並顯示新的 Fqdn，以顯示要傳送 Fabrikam 之要求的位置。
  
## <a name="dns-load-balancing"></a>DNS 負載平衡
<a name="BK_NameSIP"> </a>

您可以使用 DNS 在設定成伺服器集區的數部伺服器間共用流量負載。 若要這麼做，您可以為集區的 FQDN 建立數個記錄，每個記錄指向集區中節點的 IP 位址。
  
請參閱 [DNS 負載平衡](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) 以取得額外的負載平衡討論。
