---
title: 規劃 VDI 環境中的商務用 Skype
author: HowlinWolf-92
ms.author: v-mahoffman
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: 本主題討論連接至遠端虛擬桌面時使用商務用 Skype 的規劃考慮。
ms.openlocfilehash: 63dbdb11abf6188cb11d5f96b54ddeb541f1b9fe
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864720"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>規劃 VDI 環境中的商務用 Skype
 
本主題討論連接至遠端虛擬桌面時使用商務用 Skype 的規劃考慮。 
  
在安全性與合規性問題尤其敏感的某些組織中，會使用 (VDI) 環境的虛擬桌面基礎結構。 他們的使用者可以使用遠端桌面服務或類似的遠端連線，在虛擬桌面執行其所有的桌面應用程式和檔案。 在連線時使用商務用 Skype 搭配完整的音訊和影片，需要在主機電腦上的用戶端上大量載入音訊和視頻處理。 其他的 VDI 外掛程式軟體可讓您將處理常式降至使用者的本機電腦，並減少虛擬機器的負載。
  
有三個可用於 VDI 外掛程式元件的解決方案，由 Microsoft、Citrix 或 VMWare 提供。 針對新的部署，Microsoft 建議使用 Citrix HDX 即時優化套件解決方案或 VMWare 地平線虛擬化套件。 原始的 Lync VDI 外掛程式仍可支援其生命週期的其餘部分。
  
- **lync 的 VDI 外掛程式** 是針對 lync 2013 開發的，且與在虛擬機器上執行的 lync 2013 或商務用 Skype 2015 用戶端相容。 它是安裝在本機電腦上的獨立應用程式，可讓本機音訊和影片裝置使用於虛擬機器上的用戶端。 外掛程式不需要在本機電腦或瘦用戶端上安裝商務用 Skype 用戶端，必須執行 Windows 7、Windows 8 或 Windows Server 2008 作業系統。 使用這些作業系統及 Microsoft 支援的瘦用戶端裝置 (包括： Dell Wyse Z90D7、Dell Wyse R90L7、Dell Wyse X90m7、HP t610 和 HP t5740e。 ) 仍支援此外掛程式，但不會規劃未來的更新。 針對 Citrix 型虛擬環境，建議使用 Citrix 即時優化套件。
    
- 在 lync VDI 外掛程式上建立 **Citrix 即時優化套件**，並在虛擬機器上與 lync 2013 或商務用 Skype 2016 用戶端搭配運作。 它是由 Citrix 和 Microsoft 共同開發，可在原始的 VDI 外掛程式進行改進。 它可以安裝在含 Windows 和非 Windows 作業系統的用戶端， (包括 Windows 10、Mac 和 Linux) 。 它包含兩個元件：在虛擬機器上安裝的即時連接器 (，也就是安裝在使用者本機電腦) 上的即時媒體引擎) 和即時媒體引擎 (。 這兩個元件可讓使用者的本機電腦使用虛擬機器上執行的商務用 Skype 用戶端，將 A/V 處理移至本機電腦。 針對 Citrix 型虛擬桌面環境，建議使用 Citrix 即時優化套件，並規劃進一步的支援。
    
- 用於商務用 Skype 的 **VMWare 地平線虛擬化套件**，在與 VMWare 共同作業時，可讓您在虛擬桌面中供應商務用 Skype，同時提供極佳的使用者經驗。 此解決方案的運作方式是利用用戶端的媒體引擎建立優化的解決方案，用戶端端點提供媒體卸載功能以進行音訊和視頻通話。 這種解決方案可以直接在端點之間傳送一個單一的共同作業，或將其卸載至中央 Multipoint Control Unit (MCU) ，以供多方會議通話或會議使用。
    
> [!NOTE]
> 使用 Citrix HDX 即時優化套件或「VMWare 地平線虛擬化套件」時，不支援商務用 Skype 基本用戶端。 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX 即時優化套件
<a name="Citrix_RT"> </a>

Citrix 的 VDI 環境外掛程式 (XenApp 和 XenDesktop) 的功能可與 Lync 2013 相容，2016 2015 並使用任何按一下以執行安裝程式，或在已安裝于虛擬桌面的用戶端年1商務用 Skype 2017 月之後發行的 MSI 安裝程式。 其整體運作方式是以 Microsoft Lync VDI 外掛程式為基礎，但可在各種各樣的用戶端作業系統（包括 Windows 10、Macintosh 及 Linux）上運作。
  
在將[Microsoft 商務用 Skype 提供給 XenApp 和 XenDesktop 使用者](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)的 Citrix 網站上，可以找到完整的功能和支援的技術清單。
  
如需詳細資訊，請參閱下列連結：
  
- Citrix [HDX 即時優化套件 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [技術概述](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 商務用 Skype 功能支援](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMWare 地平線虛擬化套件
<a name="Citrix_RT"> </a>

VMWare 的 VDI 環境解決方案與安裝在虛擬機器上商務用 Skype 2015 和2016完整用戶端相容。 其整體運作方式是以 Microsoft Lync VDI 外掛程式為基礎，但可在各種各樣的用戶端作業系統（包括 Windows 10、Macintosh 及 Linux）上運作。 
  
您可以在 VMWare 網站上透過下列連結找到功能及支援技術的完整討論：
  
- [VMware 地平線 7.4 &amp; 水準用戶端4.7 的新功能](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [商務用 Skype 的地平線虛擬化套件](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [具有 VMWare 水準的 Microsoft 商務用 Skype](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Microsoft 的 Lync VDI 外掛程式
<a name="Citrix_RT"> </a>

透過 microsoft Lync vdi 外掛程式解決方案，使用者必須在 Windows 電腦或瘦用戶端上，並安裝 Microsoft 的 Lync VDI 外掛程式，以處理來自虛擬機器上之用戶端的音訊/視頻資料流程。 使用者將會：
  
1. 連線音訊/影片裝置 (如耳機或相機) 至本機電腦。
    
2. 連線至具有 Lync 2013 或商務用 Skype 2015 用戶端的遠端虛擬機器。
    
3. 在虛擬機器上輸入商務用 Skype 的認證。
    
4. 請重新輸入使用者認證，以與本機 Windows 電腦或瘦用戶端上的 Lync VDI 外掛程式建立連線。
    
建立連線之後，使用者就可以開始和接收音訊和影片通話。 網路上的流量和虛擬機器上的負載會最小化，因為本機電腦會處理音訊/視頻處理。
  
Microsoft 的 Lync VDI 外掛程式只在特定 Windows 作業系統上支援，且只支援 Lync 2013 或商務用 Skype 2015 用戶端。 如需支援的技術和限制，請參閱 [支援的虛擬化技術與已知限制](vdi-environments.md#Supported_virt) 。
  
如需詳細資訊，請參閱下列連結：
  
- [支援的虛擬化技術與已知限制](vdi-environments.md#Supported_virt)
    
- [Lync VDI 外掛程式必要條件](vdi-environments.md#VDI_prereq)
    
- [使用商務用 Skype Server 部署 Lync VDI 外掛程式](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Citrix 知識中心文章 [CTX138408](https://support.citrix.com/article/CTX138408)
    
Microsoft VDI 外掛程式可從 [Microsoft LYNC vdi 2013 外掛程式 (32 位) ](https://www.microsoft.com/download/details.aspx?id=35457) 或 [microsoft Lync vdi 2013 外掛程式 (64 bit) ](https://www.microsoft.com/download/details.aspx?id=35454)。 儘管名稱是商務用 Skype 2015 用戶端支援此外掛程式。
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>支援的虛擬化技術與已知限制
<a name="Supported_virt"> </a>

Lync VDI 外掛程式允許音訊和視頻通話支援的虛擬化技術。 在遵守標準電話規定時，也會包含對 E911 的支援。 下列各節說明 Lync VDI 外掛程式支援的虛擬化技術與已知的功能限制。
  
#### <a name="support-for-virtualization-technologies"></a>虛擬化技術的支援

Lync VDI 外掛程式支援個人虛擬桌面案例中的完整桌面遠端會話，但不支援在遠端桌面會話案例中。 您可以將這些案例描述如下：
  
- **支援：個人化虛擬桌面或虛擬桌面基礎結構 (VDI) 。** 在此案例中，每一位使用者都登入至可自訂的虛擬桌面機，而且能夠將保留在會話中的檔案儲存在桌面機上。 Microsoft 遠端桌面服務和 VMware 水準模式是已測試為搭配商務用 Skype 2015 的範例實施方案。 其他進行驗證的實施包括 Citrix XenDesktop。 如需廠商特有的 VDI 環境及已由 Microsoft 測試的用戶端硬體資訊，請參閱 [Microsoft Lync 的基礎結構限定](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)。
    
- **不支援：遠端桌面會話。** 在此案例中，每一位使用者都登入無法自訂的一般虛擬桌面會話。 範例包括 (RDSH) 和 citrix XenApp 與 citrix 接收器結合的 Microsoft 遠端桌面會話。
    
Lync VDI 外掛程式不支援其他虛擬化技術（例如 application virtualization），允許使用應用程式，而不需要在本機安裝完整的應用程式。 範例實現包括 Citrix XenApp 和 Microsoft Application Virtualization (App-V) 。 應用程式流式處理、應用程式遠端處理和混合虛擬化模式 (例如，不支援完整桌面遠端) 中的應用程式遠端處理。
  
Lync VDI 外掛程式的設計目的是使用獨立于平臺的 APIs，稱為動態虛擬通道 (Dvc) 。 針對未明確支援的案例，請參閱 VDI 解決方案提供者的支援聲明。
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Lync VDI 外掛程式必要條件
<a name="VDI_prereq"> </a>

在 VDI 環境中，虛擬機器和使用者的本機電腦必須符合本節所述的需求。
  
> [!NOTE]
>  您的虛擬化解決方案供應商可以提供如何安裝及部署其環境的詳細資料。 如需根據 Hyper-V 和遠端桌面服務部署虛擬化環境的一般資訊，請參閱 Microsoft Library： [Hyper-V](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753637(v=ws.10))中的[遠端桌面服務，Windows Server 2008 R2](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd736539(v=ws.10))中的下列文章 
  
虛擬機器必須設定 Windows 8、Windows 7 或 Windows Server 2008 R2 搭配最新的 service pack。
  
使用者的本機電腦必須符合下列需求：
  
- 使用者必須位於商務用 Skype Server 或 Lync Server 2013。
    
- 本機電腦必須執行 Windows 內嵌式 Standard 7 搭配 SP1，Windows 7 使用 SP1 或 Windows 8。
    
- 如果您使用的是遠端桌面服務，請選擇32位或64位的 Lync VDI 外掛程式，以符合本機電腦的作業系統。 本機電腦和虛擬機器都不需要有32位或64位作業系統。 如果您使用的是其他虛擬化解決方案或平臺，請參閱提供者的需求。
    
- 本機電腦必須執行 [最新版本的遠端桌面用戶端](/windows-server/remote/remote-desktop-services/clients/remote-desktop-clients)。 從 Microsoft 或您的虛擬化解決方案供應商，安裝遠端桌面服務用戶端的最新更新（或最新的遠端桌面用戶端軟體）。 
    
- 在本機電腦上，必須設定遠端桌面用戶端設定，以便在本機電腦上播放音訊，並停用遠端錄製。 若要在 Windows 中為遠端桌面連線設定這些設定，請參閱下一節「設定遠端桌面連線設定」。 
    
Microsoft VDI 外掛程式可從 [Microsoft LYNC vdi 2013 外掛程式 (32 位) ](https://www.microsoft.com/download/details.aspx?id=35457) 或 [microsoft Lync vdi 2013 外掛程式 (64 bit) ](https://www.microsoft.com/download/details.aspx?id=35454)。
  
#### <a name="known-feature-limitations"></a>已知的功能限制
<a name="VDI_prereq"> </a>

當您在 VDI 環境中使用商務用 Skype 2015 用戶端時，會有下列已知限制：
  
「呼叫委派」和「回應群組代理程式」匿名功能的支援有限。
  
不支援以下功能：
  
- 整合式音訊裝置及視訊裝置調整頁面。
    
- 多 view 影片。
    
- 錄製交談。
    
- 以匿名方式加入會議 (也就是說，加入由未與您組織) 同盟之組織所主控商務用 Skype 會議。
    
- 使用 Lync VDI 外掛程式和 Lync 電話 Edition 裝置。
    
- 在網路中斷連線的情況下延續通話。
    
- 自訂鈴聲和暫止的音樂功能。
    
Microsoft 365 或 Office 365 環境中不支援 Lync VDI 外掛程式。
  
> [!NOTE]
> Citrix 即時優化套件支援 Microsoft 365 和 Office 365。 針對 Citrix 型虛擬環境，請參閱 Citrix 的 [技術綜述](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) 檔，以取得支援的功能和版本清單。
  
## <a name="see-also"></a>另請參閱
<a name="Citrix_RT"> </a>

[使用商務用 Skype Server 部署 Lync VDI 外掛程式](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)