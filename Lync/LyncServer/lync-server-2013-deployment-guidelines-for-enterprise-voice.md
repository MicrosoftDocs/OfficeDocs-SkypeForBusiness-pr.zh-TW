---
title: Lync Server 2013： Enterprise Voice 的部署指導方針
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05cde2a845dd6314d8822e6b58445eed5c6a1d19
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531070"
---
# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 中 Enterprise Voice 的部署指導方針

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

本主題說明當您規劃部署 Lync Server 2013 和 Enterprise Voice 工作負載時，應考慮的必要條件和其他指導方針。

<div>

## <a name="deployment-prerequisites"></a>部署必要條件

若要在部署企業語音時獲得最佳的體驗，請確定您的 IT 基礎結構、網路和系統都符合下列必要條件：

  - Lync Server 2013 Standard Edition 或 Enterprise Edition 已安裝且可在您的網路上運作。

  - 所有 Edge Server 都會在周邊網路中部署並運作，包括具有 Access Edge service 的 Edge Server、A/V Edge service、Web 會議 Edge service 及反向 proxy。

  - 有一或多個使用者已建立並啟用 Lync Server。

  - Microsoft Exchange Server 2007 Service Pack 1 (SP1) 或最新的 service pack，或已安裝 Microsoft Exchange Server 2010。 其中一種方式是將 Exchange 整合通訊 (UM) 與 Lync Server 整合，並提供豐富的通知及通話記錄資訊給用戶端端點。

  - 針對每個要啟用 Enterprise Voice 的使用者，會將唯一的主要電話號碼指派、正常化，並複製到 **msRTCSIP-line** 屬性。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 支援 e.164 號碼和非直接向內撥號 (已) 號碼。 未做的號碼可以以 e.164 <STRONG> &lt; &gt; ; ext = &lt; 副檔名 &gt; </STRONG>或數位字串表示，必須是整個企業中的私人分機是唯一的。 例如，1001的私營號碼可以表示為 <STRONG>+ 1425550100、ext = 1001</STRONG>或 <STRONG>1001</STRONG>。 當表示為 <STRONG>1001</STRONG>時，預期是整個企業中的此私人號碼是唯一的。

    
    </div>

  - 部署 Enterprise Voice 的系統管理員應為 RTCUniversalServerAdmins 群組的成員。

  - 至少已成功部署 Office Communicator 2007。 若要使用此版本的新功能，請部署 Lync 2013。

  - 使用 Microsoft 或協力廠商憑證授權單位 (CA) 基礎結構，部署及設定 MKI) 的 Managed key 基礎 (結構。

  - 安裝轉送伺服器的每一部電腦都必須是：
    
      - 網域的成員伺服器，並為 Active Directory 網域服務做好準備。 如需 Active Directory 網域服務的準備程式，請參閱部署檔中的 [準備 Lync Server 2013 的 Active Directory 網域服務](lync-server-2013-preparing-active-directory-domain-services.md) 。
    
      - 執行下列其中一個作業系統：
        
          - <span></span>  
            64位版本的 Windows Server 2008 Standard 作業系統
        
          - <span></span>  
            64位版本的 Windows Server 2008 企業版作業系統

  - 若連到公用交換電話網路的連線 (PSTN) 或私營分公司 exchange (PBX) 是透過一種時間分割多工 (TDM) 連線，則可以部署一或多個 PSTN 閘道。  (如果是透過 SIP 主幹連線，則不需要 PSTN 閘道。 ) 

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a>電源、網路或電話語音中斷

如果您所在位置出現電源、網路或電話語音中斷、中斷或其他問題，則語音、立即訊息、目前狀態，以及 Lync Server 及任何連接至 Lync Server 之裝置的其他功能都可能無法正常運作。

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a>Enterprise Voice 取決於伺服器可用性和語音用戶端和硬體可操作性

與 Lync Server 的語音通訊取決於伺服器軟體的可用性，以及連接至伺服器軟體的語音用戶端或硬體電話裝置是否可正常運作。

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a>存取緊急服務的替代方法

針對您安裝語音用戶端 (的位置（例如，執行 Lync 用戶端或 Lync Phone Edition 裝置) 的電腦，我們建議您維護備份選項，讓使用者呼叫緊急服務 (例如，911或 999) 以防電源故障、網路連線能力降低、電話語音中斷，或可能阻礙 Lync Server、Lync 或 Lync Phone Edition 裝置運作的其他問題。 這類替代選項可以包含連線到標準公用交換電話網路 line 或蜂窩電話的電話。

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a>緊急電話和多行電話系統

使用多行電話系統 (MLTS) 可能受制于 U.S 州或聯邦法律或其他國家/地區的法律，也就是當來電者進入緊急服務時，需要 MLTS 提供來電者的電話號碼、分機和/或實體位置，以供來電者使用時 (例如，撥號緊急存取號碼，例如911或 999) 。 在此版本中，Lync Server 可以設定為向緊急服務提供者提供來電者的實體位置，如在 [Lync Server 2013 中規劃緊急服務 (E9-1-1) ](lync-server-2013-planning-for-emergency-services-e9-1-1.md)所述。 遵守 MLTS 法律是 Lync Server、Lync 用戶端和 Lync Phone Edition 裝置的買方的唯一責任。

</div>

</div>

<span> </span>

</div>

</div>

</div>

