---
title: Lync Server 2013：Enterprise Voice 的部署指導方針
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0f4f6198f8fb82720834d112bcf363554aaf84d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 中 Enterprise Voice 的部署指導方針

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

本主題說明當您規劃要部署 Lync Server 2013 和企業語音工作負載時，要考慮的先決條件及其他指導方針。

<div>

## <a name="deployment-prerequisites"></a>部署先決條件

若要在部署企業語音時獲得最佳體驗，請確定您的 IT 基礎結構、網路和系統符合下列先決條件：

  - Lync Server 2013 標準版或 Enterprise Edition 已安裝並在您的網路上運作。

  - 所有邊緣伺服器都是在您的周邊網路中部署和運作，包括具有存取邊緣服務的邊緣伺服器、A/V 邊緣服務、網頁會議 Edge 服務，以及反向 proxy。

  - 已為 Lync Server 建立並啟用一或多位使用者。

  - [Microsoft Exchange Server 2007 Service Pack 1 （SP1）] 或 [最新 Service pack] 或 [Microsoft Exchange Server 2010 已安裝]。 這其中一個是將 Exchange 整合通訊（UM）與 Lync Server 整合所需，並提供豐富的通知及通話記錄資訊給用戶端端點。

  - 已針對要啟用企業語音的每位使用者，將唯一的主要電話號碼指派、標準化，並複製到**msRTCSIP**屬性。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 支援 E. 164 個數字和非直接撥入式撥號（已有）號碼。 非使用中的數位可以用<STRONG> &lt;E. 164&gt;; ext =&lt;extension&gt; </STRONG>或數位字串來表示，且要求私人副檔名在整個企業中都是唯一的。 例如，1001的私用號碼可以表示為<STRONG>+ 1425550100; ext = 1001</STRONG>，或<STRONG>1001</STRONG>。 當表示為<STRONG>1001</STRONG>時，預期是該私人數位在整個企業中都是唯一的。

    
    </div>

  - 部署企業語音的系統管理員應該是 RTCUniversalServerAdmins 群組的成員。

  - Office Communicator 2007 至少已成功部署。 若要使用此版本的新功能，請部署 Lync 2013。

  - 管理的金鑰結構（MKI）是使用 Microsoft 或協力廠商憑證授權單位（CA）基礎結構來部署和設定。

  - 安裝轉送伺服器的每台電腦都必須是：
    
      - 網域的成員伺服器，並準備好使用 Active Directory 網域服務。 如需 Active Directory 網域服務的準備程式，請參閱在部署檔中[為 Lync Server 2013 準備 Active Directory 網域服務](lync-server-2013-preparing-active-directory-domain-services.md)。
    
      - 執行下列其中一個作業系統：
        
          - <span></span>  
            Windows Server 2008 標準作業系統的64位版本
        
          - <span></span>  
            Windows Server 2008 Enterprise 作業系統的64位版本

  - 如果連線到公用交換式電話網絡（PSTN）或私人分支交換（PBX）是透過時間除法複用（TDM）連線，則可以使用一或多個 PSTN 閘道進行部署。 （如果連線是透過 SIP 幹線來進行，則不需要 PSTN 閘道。）

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a>電源、網路或電話語音中斷

如果您所在位置有停機、中斷或其他電源、網路或電話語音的下降，請語音、立即訊息、目前狀態，以及 Lync Server 和任何連接至 Lync Server 的裝置都可能無法正常運作。

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a>企業語音依賴伺服器可用性與語音用戶端及硬體可操作性

使用 Lync Server 的語音通訊，取決於伺服器軟體的可用性，以及連線到伺服器軟體的語音用戶端或硬體電話裝置是否正常運作。

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a>存取緊急服務的替代方法

針對您安裝語音用戶端的位置（例如，執行 Lync 用戶端或 Lync 手機版裝置的電腦），建議您維護備份選項，讓使用者呼叫緊急服務（例如，911或999）以防電源故障、網路連線能力下降、電話語音中斷或其他可能會阻礙 Lync Server、Lync 或 Lync Phone Edition 裝置運作的問題。 這類替代選項可以包含連線至標準公用交換電話網絡線路或手機的電話。

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a>緊急通話和多行電話系統

使用多行電話系統（MLTS）可能受限於美國州或聯邦法律，或其他國家/地區的法律，需要 MLTS 來提供來電者的電話號碼、延伸及/或物理位置給緊急服務（例如，當您撥打緊急存取號碼，例如911或999）。 在這個版本中，Lync Server 可以設定為向緊急服務提供者提供來電者的物理位置，如在[Lync Server 2013 的緊急服務（E9-1）中](lync-server-2013-planning-for-emergency-services-e9-1-1.md)所述。 遵守 MLTS 法律是 Lync Server、Lync 用戶端和 Lync Phone Edition 裝置的購買者的唯一責任。

</div>

</div>

<span> </span>

</div>

</div>

</div>

