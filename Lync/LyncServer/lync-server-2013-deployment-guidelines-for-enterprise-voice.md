---
title: 'Lync Server 2013: Enterprise voice 的部署指導方針'
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
ms.openlocfilehash: 688cf48c7f716047f0d7412c34ce84006a5a9348
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 中的 Enterprise voice 的部署指導方針

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-21_

本主題說明先決條件和其他您計劃要部署 Lync Server 2013 和 Enterprise Voice 工作負載時所應考量的指導方針。

<div>

## <a name="deployment-prerequisites"></a>部署必要條件

部署 Enterprise Voice 時獲得最佳體驗，請確認您的 IT 基礎結構、 網路和系統都符合下列先決條件：

  - Lync Server 2013 Standard Edition 或 Enterprise Edition 已安裝且正在運作您網路上。

  - 所有 Edge Server 都都已部署、 作業在周邊網路，包括 Edge Server 與 Access Edge service，A / V Edge service、 Web Conferencing Edge service 和反向 proxy。

  - 已建立並啟用 Lync Server 的一或多個使用者。

  - 已安裝 Microsoft Exchange Server 2007 Service Pack 1 (SP1) 或最新的 service pack 或 Microsoft Exchange Server 2010。 其中，才能將 Exchange 整合通訊 (UM) 整合搭配 Lync Server，以及用於提供豐富的通知及通話記錄資訊用戶端端點。

  - 唯一的主要電話號碼已指定正規化，並複製到每個使用者啟用 Enterprise voice **msrtcsip-line**屬性。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 支援 E.164 號碼和非-直接向內撥號 DID 號碼。 非-DID 號碼可以表示格式<STRONG>&lt;E.164&gt;; ext =&lt;分機&gt;</STRONG>或數字，整個企業的私用的分機號碼是唯一的需求與的字串。 例如，以表示 1001年專用號碼<STRONG>+1425550100; ext = 1001年</STRONG>，或為<STRONG>1001年</STRONG>。 代表<STRONG>1001年</STRONG>，預期時，此私用的數字是唯一的整個企業。

    
    </div>

  - 部署 Enterprise Voice 的系統管理員應該是 RTCUniversalServerAdmins 群組的成員。

  - 在最低限度下，Office Communicator 2007 是成功部署。 若要使用功能新增至這個版本，就會部署 Lync 2013。

  - 受管理的公開金鑰基礎結構 (MKI) 是部署和設定，使用 Microsoft 或協力廠商憑證授權單位 (CA) 基礎結構。

  - 必須為每一部電腦安裝中繼伺服器：
    
      - 成員伺服器的網域，並為 Active Directory 網域服務準備。 如需 Active Directory 網域服務準備程序，請參閱部署文件中的[準備 Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) 。
    
      - 執行下列其中一個下列作業系統：
        
          - <span></span>  
            Windows Server 2008 Standard 作業系統 64 位元版本
        
          - <span></span>  
            Windows Server 2008 Enterprise 作業系統 64 位元版本

  - 利用時間部門多工 (TDM) 連線至公用交換的電話網路 (PSTN) 或專用交換機 (PBX) 的連線時，一或多個 PSTN 閘道可供部署。 （如果透過 SIP 主幹連線，PSTN 閘道不是必要。）

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a>電力、 網路或電話服務中斷

如果沒有中斷、 干擾或其他降低電力、 網路或電話服務所在位置，語音、 立即訊息、 目前狀態和 Lync Server 與任何裝置連線至 Lync Server 的其他功能可能無法正常運作。

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a>Enterprise Voice 取決於伺服器的可用性和 Voip 用戶端與硬體的可操作性

語音通訊與 Lync Server 取決於伺服器軟體的可用性，以及語音用戶端或硬體電話裝置連接到伺服器軟體的正常運作。

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a>連絡緊急服務的替代方法

針對您安裝的語音用戶端 （例如，電腦執行 Lync 用戶端或 Lync Phone Edition 裝置） 這些位置，我們建議您電源失敗的情況下，維護備份的選項，讓使用者呼叫緊急服務 （例如，911 或 999）網路連線效能下降、 電話服務中斷或其他問題，可能會抑制 Lync 伺服器、 Lync 或 Lync Phone Edition 裝置的作業。 這類替代選項可以包括標準的公用交換的電話網路線路或行動電話連線的電話。

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a>緊急救援電話與多線路電話系統

多行的電話系統 (MLTS) 使用可能需支付美國狀態或聯邦法律或其他國家/地區需要提供來電者的電話號碼、 副檔名及/或適用的緊急服務的實體位置時，來電者 MLTS 的法律撥至緊急服務 （例如，例如 911 或 999 緊急存取號碼來撥號時）。 在此版本中，可以設定 Lync Server[規劃緊急服務 (E9-1-1)，在 [Lync Server 2013 ](lync-server-2013-planning-for-emergency-services-e9-1-1.md)中所述，提供發話者的實體位置與緊急服務提供者。 與 MLTS 法律合規性是唯一的 Lync Server，Lync 用戶端和 Lync Phone Edition 裝置購買者的責任。

</div>

</div>

<span> </span>

</div>

</div>

</div>

