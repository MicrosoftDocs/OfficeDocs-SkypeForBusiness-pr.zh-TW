---
title: 規劃 VDI 環境中的商務用 Skype
author: lanachin
ms.author: v-lanac
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: 本主題討論在連線至遠端虛擬桌面時，使用商務用 Skype 的規劃考慮。
ms.openlocfilehash: d2d65167eb574d17e31c19759364841147af6c05
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803503"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>規劃 VDI 環境中的商務用 Skype
 
本主題討論在連線至遠端虛擬桌面時，使用商務用 Skype 的規劃考慮。 
  
虛擬桌面基礎結構（VDI）環境是在安全性與合規性問題特別敏感的一些組織中使用。 他們的使用者使用遠端桌面服務或類似的遠端連線，在虛擬桌面完成其工作（含所有桌面應用程式和檔案）。 在連線時使用商務用 Skype，在連線時，在用戶端上的音訊和視頻處理需要大量載入，才能在虛擬機器上託管。 您可以使用其他 VDI 外掛程式軟體，將該處理減輕到使用者的本機電腦，並減少虛擬桌面機的負載。
  
有三個解決方案可供 Microsoft、Citrix 或 VMWare 提供的 VDI 外掛程式元件使用。 針對新的部署，Microsoft 建議使用 Citrix HDX 即時優化套件方案或 VMWare 地平線虛擬化套件。 原始的 Lync VDI 外掛程式在其整個生命週期的剩餘部分中仍然受到支援。
  
- Lync **VDI 外掛程式**是針對 lync 2013 開發的，且與在虛擬機器上執行的 lync 2013 或商務用 Skype 2015 用戶端相容。 它是安裝在本機電腦上的獨立應用程式，可讓您在虛擬機器上使用本機音訊和視頻裝置搭配用戶端使用。 外掛程式不需要在本機電腦或瘦用戶端上安裝商務用 Skype 用戶端，必須執行 Windows 7、Windows 8 或 Windows Server 2008 作業系統。 （使用這些作業系統並受 Microsoft 支援的瘦用戶端裝置包括： Dell Wyse Z90D7、戴爾 Wyse R90L7、Dell Wyse X90m7、HP t610 和 HP t5740e。）此外掛程式仍受到支援，但將來沒有規劃任何更新。 對於基於 Citrix 的虛擬環境，建議使用 Citrix 即時優化套件。
    
- **Citrix 即時優化套件**是在 lync VDI 外掛程式上建立，且可與 Lync 2013 或虛擬機器上的商務用 Skype 2016 用戶端搭配使用。 它由 Citrix 與 Microsoft 共同開發，可在原始的 VDI 外掛程式上改善。 它可以安裝在裝有 Windows 和非 Windows 作業系統（包括 Windows 10、Mac 和 Linux）的用戶端。 它包含兩個元件：即時連接器（安裝在虛擬桌面）和即時媒體引擎（在最終使用者的本機電腦上安裝）。 這兩個元件可讓使用者的本機電腦使用在虛擬機器上執行的商務用 Skype 用戶端，並將 A/V 處理移至本機電腦。 針對基於 Citrix 的虛擬桌面環境，我們建議使用 Citrix 即時優化套件，並規劃進一步的支援。
    
- 商務用 Skype 的**VMWare 地平線虛擬化套件**是與 VMWare 共同作業，可讓您在虛擬桌面中傳送商務用 skype，同時提供絕佳的使用者體驗。 此方案的運作方式是，利用用戶端的媒體引擎來建立優化的解決方案，並讓用戶端端點提供媒體卸載功能以進行音訊與視頻通話。 這個解決方案可以在一對一共同作業的端點之間直接傳送音訊及視頻，或將它移到多方會議通話或會議的中央 Multipoint 控制單元（MCU）。
    
> [!NOTE]
> Citrix HDX 即時優化套件或 VMWare 地平線虛擬化套件不支援商務用 Skype 基本用戶端。 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX 即時優化套件
<a name="Citrix_RT"> </a>

Citrix 的 VDI 環境外掛程式（XenApp 和 XenDesktop）與 Lync 2013 和商務用 Skype 2015 和2016（使用任何按一下以執行安裝程式的完整用戶端，或在已安裝在虛擬機器上的 MSI 安裝程式2017之後發行）用戶端桌面. 它的整體運作方式是以 Microsoft Lync VDI 外掛程式為基礎，但在各種用戶端作業系統（包括 Windows 10、Macintosh 及 Linux）上都能運作。
  
在[提供 Microsoft 商務用 Skype XenApp 和 XenDesktop 使用者](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)的 Citrix 網站上，可以找到完整的功能清單及支援的技術。
  
如需詳細資訊，請參閱下列連結：
  
- Citrix [HDX 即時優化套件 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [技術概述](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 商務用 Skype 功能支援](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMWare 地平線虛擬化套件
<a name="Citrix_RT"> </a>

VMWare 的 VDI 環境解決方案與在虛擬機器上安裝的商務用 Skype 2015 和2016完整用戶端相容。 它的整體運作方式是以 Microsoft Lync VDI 外掛程式為基礎，但在各種用戶端作業系統（包括 Windows 10、Macintosh 及 Linux）上都能運作。 
  
您可以在 VMWare 網站上的下列連結中找到完整的功能和支援的技術討論：
  
- [VMware 7.4 的新功能水準 4.7 &amp;](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [商務用 Skype 的地平線虛擬化套件](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [使用 VMWare 的 Microsoft 商務用 Skype 地平線](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Microsoft 的 Lync VDI 外掛程式
<a name="Citrix_RT"> </a>

透過 Microsoft Lync VDI 外掛程式解決方案，使用者必須在 Windows 電腦或瘦用戶端，且已安裝 Microsoft 的 Lync VDI 外掛程式來處理來自虛擬機器上用戶端的音訊/視頻資料流程。 使用者會：
  
1. 將音訊/視頻裝置（例如耳機或相機）連線至本機電腦。
    
2. 使用 Lync 2013 或商務用 Skype 2015 用戶端連線到遠端虛擬機器。
    
3. 在虛擬機器上輸入商務用 Skype 的認證。
    
4. 重新輸入使用者認證，以與本機 Windows 電腦或瘦用戶端上的 Lync VDI 外掛程式建立連線。
    
建立連線之後，使用者就已準備好撥打及接聽音訊與視頻通話。 網路上的流量和虛擬機器上的負載都會最小化，因為本機電腦會處理音訊/視頻處理。
  
Microsoft 的 Lync VDI 外掛程式只受特定 Windows 作業系統支援，且只支援 Lync 2013 或商務用 Skype 2015 用戶端。 如需支援的技術與限制的詳細資料，請參閱[支援的虛擬化技術和已知限制](vdi-environments.md#Supported_virt)。
  
如需詳細資訊，請參閱下列連結：
  
- [受支援的虛擬化技術與已知限制](vdi-environments.md#Supported_virt)
    
- [Lync VDI 外掛程式先決條件](vdi-environments.md#VDI_prereq)
    
- [使用商務用 Skype Server 部署 Lync VDI 外掛程式](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Citrix 知識中心文章[CTX138408](https://support.citrix.com/article/CTX138408)
    
您可以在[Microsoft LYNC vdi 2013 外掛程式（32位）](https://www.microsoft.com/en-us/download/details.aspx?id=35457)或[microsoft lync vdi 2013 外掛程式（64位）](https://www.microsoft.com/en-us/download/details.aspx?id=35454)中使用 microsoft VDI 外掛程式。 商務用 Skype 2015 用戶端（無論名稱）都支援此外掛程式。
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>受支援的虛擬化技術與已知限制
<a name="Supported_virt"> </a>

Lync VDI 外掛程式可支援音訊及視頻通話（支援的虛擬化技術）。 在遵守標準電話規章的情況下，也包含對 E911 的支援。 下列各節說明 Lync VDI 外掛程式所支援的虛擬化技術和已知的功能限制。
  
#### <a name="support-for-virtualization-technologies"></a>對虛擬化技術的支援

Lync VDI 外掛程式支援個人虛擬桌面案例中的完整桌面遠端會話，但在遠端桌面會話案例中則不支援。 這些案例的描述如下：
  
- **支援：個人化虛擬桌面或虛擬桌面基礎結構 (VDI)。 ** 在這個案例中，每位使用者登入自訂的虛擬桌面，並且能儲存在所有工作階段均會顯示的桌面上的檔案。 Microsoft 遠端桌面服務和 VMware 地平線模式是經過測試，可搭配商務用 Skype 2015 使用的範例實現。 進行驗證的其他實施包括 Citrix XenDesktop。 如需有關已由 Microsoft 測試的供應商專用 VDI 環境及用戶端硬體的相關資訊，請參閱[Microsoft Lync 合格的基礎結構](https://go.microsoft.com/fwlink/?LinkID=313435)。
    
- **不支援：遠端桌面工作階段。 ** 在這種情況下，每個使用者都會登入不能自訂的一般虛擬桌面會話。 範例包括與 Citrix 接收器結合的 Microsoft 遠端桌面會話（RDSH）和 Citrix XenApp。
    
Lync VDI 外掛程式不支援其他虛擬化技術（例如應用程式虛擬化），可讓您使用應用程式，而不需要在本機安裝完整的應用程式。 範例實現包括 Citrix XenApp 和 Microsoft Application Virtualization （App-v）。 不支援應用程式流式處理、應用程式遠端處理及混合式虛擬化模式（例如，完整桌面遠端處理中的應用程式遠端處理）。
  
Lync VDI 外掛程式的設計目的是使用稱為「動態虛擬通道」（DVCs）的平臺無關 Api。 針對未明確支援的案例，請參閱來自 VDI 解決方案提供者的支援聲明。
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Lync VDI 外掛程式先決條件
<a name="VDI_prereq"> </a>

在 VDI 環境中，虛擬機器與使用者的本機電腦必須符合本節中所述的需求。
  
> [!NOTE]
>  您的虛擬化解決方案提供者可以提供如何安裝及部署其環境的詳細資料。 如需有關根據 Hyper-v 和遠端桌面服務部署虛擬化環境的一般資訊，請參閱 Microsoft 文件庫中的下列文章： [hyper-v](https://go.microsoft.com/fwlink/p/?linkid=247514)、 [Windows Server 2008 R2 中的遠端桌面服務](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
虛擬機器必須使用 Windows 8、Windows 7 或 Windows Server 2008 R2 （含最新的 service pack）進行設定。
  
使用者的本機電腦必須符合下列需求：
  
- 使用者必須駐留在商務用 Skype Server 或 Lync Server 2013 上。
    
- 本機電腦必須執行 Windows Embedded Standard 7 （含 SP1）、Windows 7 （含 SP1）或 Windows 8。
    
- 如果您使用的是遠端桌面服務，請選擇32位或64位的 Lync VDI 外掛程式，以符合本機電腦的作業系統。 本機電腦和虛擬電腦不需要有32位或64位的作業系統。 如果您使用的是其他虛擬化解決方案或平臺，請參閱提供者的需求。
    
- 本機電腦必須執行[最新版本的遠端桌面用戶端](https://go.microsoft.com/fwlink/p/?LinkId=268032)。 從您的虛擬化方案提供者，從 Microsoft 或最新的遠端桌面用戶端軟體，安裝遠端桌面服務用戶端的最新更新。 
    
- 在本機電腦上，必須設定遠端桌面用戶端設定，以便在本機電腦上播放音訊，並停用遠端錄製。 若要在 Windows 中設定遠端桌面連線的這些設定，請參閱下一節「設定遠端桌面連線設定」。 
    
您可以在[Microsoft LYNC vdi 2013 外掛程式（32位）](https://www.microsoft.com/en-us/download/details.aspx?id=35457)或[microsoft lync vdi 2013 外掛程式（64位）](https://www.microsoft.com/en-us/download/details.aspx?id=35454)中使用 microsoft VDI 外掛程式。
  
#### <a name="known-feature-limitations"></a>已知的功能限制
<a name="VDI_prereq"> </a>

當您在 VDI 環境中使用商務用 Skype 2015 用戶端時，以下是已知的限制：
  
通話委派與回應群組代理匿名功能的支援有限。
  
不支援以下功能：
  
- 整合式音訊裝置及視訊裝置調整頁面。
    
- 多重檢視視訊。
    
- 錄製交談。
    
- 匿名加入會議（也就是加入不與貴組織聯盟之組織託管的商務用 Skype 會議）。
    
- 將 Lync VDI 外掛程式與 Lync Phone Edition 裝置搭配使用。
    
- 在網路中斷連線的情況下延續通話。
    
- 自訂鈴聲及通話保留音樂功能。
    
在 Office 365 環境中不支援 Lync VDI 外掛程式。
  
> [!NOTE]
> Citrix 即時優化套件支援 Office 365。 針對基於 Citrix 的虛擬環境，請參閱 Citrix 的[技術綜述](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl)檔，瞭解支援的功能和版本清單。
  
## <a name="see-also"></a>另請參閱
<a name="Citrix_RT"> </a>

[使用商務用 Skype Server 部署 Lync VDI 外掛程式](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

