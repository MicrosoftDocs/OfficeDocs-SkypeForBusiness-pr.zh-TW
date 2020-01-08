---
title: Lync Server 2013 會議元件與拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5caf5ba33e863e08bf4f728d2bf11394f37f20b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的會議元件與拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-04_

當您在 [拓撲建立器] 中選取 [會議] 時，會議會作為前端伺服器或標準版伺服器的一部分來部署。 電話撥入式會議與 PowerPoint 共用需要額外的元件和設定。 下列各節說明網路會議、A/V 會議和電話撥入式會議支援的元件與拓撲。

<div>

## <a name="supported-components"></a>支援的元件

唯一的元件 web 會議與 A/V 會議需要您組織的前端伺服器或標準版伺服器。 如需前端伺服器和標準版伺服器的硬體和軟體需求清單，請參閱 lync Server 2013[支援的 Lync server 2013](lync-server-2013-supported-hardware.md)和[伺服器軟體及基礎結構支援](lync-server-2013-server-software-and-infrastructure-support.md)的硬體。

Lync Server 2013 使用 Office Web Apps 和 Office Web Apps 伺服器來處理 PowerPoint 簡報的共用和轉譯。 如需安裝及設定 Office Web Apps 伺服器的詳細資料，請參閱設定[與 Office Web Apps server 和 Lync Server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

除了適用于 web 會議和 A/V 會議的需求之外，電話撥入式會議還使用下列 Lync Server 2013 元件：

  - **應用程式服務**   應用程式服務提供部署、託管及管理整合通訊（UC）應用程式的平臺。 電話撥入式會議使用兩個需要應用程式服務的 UC 應用程式：會議助理與會議公告。 當您部署會議工作負載並選取 [電話撥入式會議] 選項時，應用程式服務預設會安裝並在每個標準版 server 上的每個前端伺服器上啟用。

  - **會議助理應用**   程式會議助理應用程式是一種整合通訊應用程式，可接受公用交換電話網絡（PSTN）通話、播放提示，以及將呼叫加入 a/V 會議。 在您部署會議工作負載及選取電話撥入式會議選項時，會議助理應用程式預設會安裝並啟用。

  - **會議發佈應用程式**   會議公告應用程式是一種整合式通訊應用程式，它會在特定動作上對 PSTN 參與者播放聲音和提示，例如當參與者加入或離開會議時，參與者是靜音或已取消靜音、有人進入會議會議廳，或會議已鎖定或解除鎖定。 [會議公告] 應用程式也支援來自電話鍵台的雙音調 multifrequency （DTMF）命令。 當您部署會議工作負載並選取 [電話撥入式會議] 選項時，會議宣告應用程式預設會自動安裝並啟用。

  - ****[電話撥入式會議設定] 頁面： [電話撥入式會議設定] 頁面會以其可用語言顯示會議撥入號碼、指派會議資訊（也就是，對於不需要排程的會議）以及會議 DTMF 控制，並支援個人識別碼（PIN）及指派會議資訊的管理。    [電話撥入式會議設定] 頁面會自動安裝為 Web 服務的一部分。

  - **Lync server 2013、中繼伺服器和 pstn 閘道**   電話撥入式會議需要一個中繼伺服器來轉譯 Lync server 2013 和 pstn 閘道之間的信號（以及在部分設定中的媒體），以及在中繼伺服器與 pstn 閘道之間轉譯信號與媒體的 pstn 閘道。 若是電話撥入式會議，您必須至少部署一個中繼伺服器，並至少進行下列其中一項作業：
    
      - PSTN 閘道
    
      - IP-PBX
    
      - 會話邊界控制器（SBC）（適用于您透過設定 SIP 主幹來連接的網際網路電話服務提供者）
    
    <div>
    

    > [!NOTE]  
    > 如果您也要部署企業語音，中繼伺服器和 PSTN 閘道是企業語音部署的一部分。 如果您沒有部署企業語音，您必須至少部署一個中繼伺服器以及至少一個 PSTN 閘道、IP PBX 或 SBC （適用于電話撥入式會議）。

    
    </div>

  - **[檔案存放區**   ] 檔案存放區用於記錄的名稱音訊檔案。 檔案存放區是每個企業版或標準版部署中的標準元件。

  - **[使用者商店**   ] 使用者商店是用來儲存使用者 Lync Server 2013 pin。 Pin 會散列。 使用者存放區是每個企業版或標準版部署中的標準元件。

  - **Lync server [控制台**   ] 中的某些撥入設定可以使用 Lync Server [控制台] 進行設定。

  - **Lync server 管理命令**   介面：您可以使用 lync server 管理命令介面 Cmdlet 來設定所有撥入設定。 Lync Server 管理命令介面 Cmdlet 可用於部署、設定、執行、監控，以及疑難排解會議助理應用程式與會議發佈應用程式。 如需特定 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。

</div>

<div>

## <a name="supported-topologies"></a>支援的拓撲

在 Lync Server 2013 中，執行會議服務的伺服器總是與前端伺服器或標準版伺服器 collocated。 在初始部署期間，拓撲建立器可讓您選擇在拓撲中包含會議。 您也可以使用拓撲建立器，將會議新增至現有的部署。 如需詳細資訊，請參閱[在 Lync Server 2013 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。

<div>

## <a name="dial-in-conferencing-toplogies"></a>電話撥入式會議 Toplogies

您可以在下列拓撲和配置中部署電話撥入式會議：

  - Lync Server 2013 標準版

  - Lync Server 2013 企業版

  - 具備或不使用企業語音

您可以在中央網站中部署應用程式服務、會議助理應用程式及會議公告應用程式，但不能在分支網站中進行。

<div>


> [!NOTE]  
> 如果您要部署電話撥入式會議，您必須在部署 Lync Server 2013 會議的每個池中部署它。 您不需要在每個池中指派存取號碼，但您必須在每個池中部署電話撥入式會議功能。 當使用者從某個池中呼叫存取號碼以在不同的池中加入 Lync Server 2013 會議時，此需求支援所記錄的名稱功能。



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a>Lync Server 2013 與 Office Web Apps 支援的拓撲

Lync Server 2013 提供下列配置 Office Web Apps 伺服器的方式。 視您的需求而定，您可以：

  - **在您組織的防火牆之後及同一網路區域中，安裝 Lync Server 2013 與 Office Web Apps Server 內部部署。** 透過此拓朴，系統將會透過您的反向 proxy 伺服器提供對 Office Web Apps 伺服器的外部存取。 Lync Server 2013 與 Office Web Apps Server （或 Office Web Apps 伺服器群）都是在內部部署和組織的防火牆後安裝。 在理想的情況下，您應該在與 Lync Server 相同的網路區域中安裝 Office Web Apps 伺服器。
    
    外部 Lync 用戶端可以使用反向 proxy 伺服器連線至 Lync Server 2013 與 Office Web Apps 伺服器，該伺服器是接受網際網路要求並將其轉寄給內部網路的伺服器。 （內部用戶端不需要使用反向 proxy 伺服器，因為它們可以直接連線到 Office Web Apps 伺服器）。如果您想要使用僅供 Lync Server 2013 使用的專用 Office Web Apps 伺服器群，此拓朴效果最佳。

  - **使用外部部署的 Office Web Apps 伺服器**
    
    在此拓朴中，Lync Server 2013 是在內部部署，並使用在 Lync Server 網路區域外部部署的 Office Web Apps 伺服器。 當 Office Web Apps Server 在公司中的多個應用程式間共用，且已部署在要求 Lync Server 使用 Office Web Apps Server 外部介面的網路（反之亦然）時，可能會發生這種情況。
    
    您不需要安裝反向 proxy 伺服器;相反地，從 Office Web Apps 伺服器到 Lync Server 2013 的所有要求都會透過您的邊緣伺服器進行路由。 您的內部和外部 Lync 用戶端都是使用外部 URL 連線到 Office Web Apps 伺服器。
    
    如果 Office Web Apps 伺服器是在您的內部防火牆外部署，請選取 [ **Office Web Apps 伺服器] 部署在拓撲結構建立器中的外部網路（也就是 [週邊/網際網路]）** 。 如需詳細資訊，請參閱設定[與 Office Web Apps server 和 Lync Server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

不論您選取何種拓撲，請務必開啟正確的防火牆埠。 您必須確認無法透過 Office Web Apps 伺服器、負載平衡器或 Lync Server 上的防火牆封鎖 DNS 名稱、IP 位址和埠。

<div>


> [!NOTE]  
> 提供外部 Office Web Apps 伺服器存取權的另一個選項就是在周邊網路中部署伺服器。 如果您選擇這樣做，請記住 Office Web Apps Server 安裝程式需要伺服器電腦成為您 Active Directory 網域的成員。 除非您的網路原則允許周邊網路中的電腦成為 Active Directory 網域成員，否則建議您不要在周邊網路中安裝 Office Web Apps 伺服器。 相反地，您應該在內部網路中安裝 Office Web Apps 伺服器，並透過您的反向 proxy 伺服器提供外部使用者存取。



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

