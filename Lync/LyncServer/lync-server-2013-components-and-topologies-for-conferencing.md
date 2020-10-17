---
title: Lync Server 2013 會議元件與拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfdb6ae250e3ccb97f044892daa8ac11e7c1b99b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502580"
---
# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的會議元件與拓撲

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-04_

當您在拓撲產生器中選取會議時，會將會議部署為前端伺服器或 Standard Edition Server 的一部分。 電話撥入式會議和 PowerPoint 共用需要其他元件和設定。 下列各節說明 web 會議、A/V 會議和電話撥入式會議所支援的元件和拓撲。

<div>

## <a name="supported-components"></a>支援的元件

只有組織的前端伺服器或 Standard Edition 伺服器，才需要 [元件 web 會議和 A/V 會議]。 如需前端伺服器和 Standard Edition server 的硬體和軟體需求清單，請參閱 Lync Server 2013 中 [支援的 Lync server 2013](lync-server-2013-supported-hardware.md) 和 [伺服器軟體和基礎結構支援](lync-server-2013-server-software-and-infrastructure-support.md)硬體。

Lync Server 2013 使用 Office Web Apps 與 Office Web apps Server 來處理 PowerPoint 簡報的共用及呈現。 如需安裝及設定 Office Web Apps Server 的詳細資訊，請參閱設定 [Office Web Apps server 與 Lync server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

除了 web 會議和 A/V 會議的需求之外，電話撥入式會議還使用下列 Lync Server 2013 元件：

  - **應用程式服務**    Application service 提供一個平臺，用以部署、主控和管理整合通訊 (UC) 應用程式。 電話撥入式會議使用需要 Application service 的兩個 UC 應用程式：會議助理和會議宣告。 當您部署會議工作負載並選取 [電話撥入式會議] 選項時，預設會在前端集區中的每一部前端伺服器及每個 Standard Edition 伺服器上安裝及啟用應用程式服務。

  - **會議助理應用程式**    會議應答應用程式是一種整合通訊應用程式，可接受公用交換電話網路 (PSTN) 通話、播放提示，以及將通話加入 A/V 會議。 當您部署會議工作負載並選取 [電話撥入式會議] 選項時，預設會安裝及啟用會議應答應用程式。

  - **會議宣告應用程式**    會議宣告應用程式是一種整合通訊應用程式，可在某些動作上為 PSTN 參與者播放色調和提示，例如當參與者加入或離開會議時，參與者會靜音或 unmuted、某人進入會議會議廳，或是鎖定或解除鎖定會議。 會議宣告應用程式也支援雙聲調頻式訊號 (DTMF) 命令從電話鍵鍵盤。 會議宣告應用程式會在您部署會議工作負載及選取電話撥入式會議選項時，依預設自動安裝及啟用。

  - **電話撥入式會議設定頁面**    [電話撥入式會議設定] 頁面會以可用的語言顯示會議撥入號碼、指派會議資訊 (，也就是針對不需要排程) 的會議，以及在會議 DTMF 控制項中管理的個人識別碼，並支援 (PIN) 和指派會議資訊的個人識別碼的管理。 [電話撥入式會議設定] 頁面會自動安裝為 Web 服務的一部分。

  - **Lync server 2013、轉送伺服器和 PSTN 閘道**    電話撥入式會議需要一台轉送伺服器，以在 Lync Server 2013 與 PSTN 閘道之間的某些設定) 中轉譯信號 (和媒體，以及在轉送伺服器和 PSTN 閘道之間轉譯信號和媒體的 PSTN 閘道。 若為電話撥入式會議，您必須至少部署一個轉送伺服器，至少要有下列其中一項：
    
      - PSTN 閘道
    
      - IP-PBX
    
      - 透過設定 SIP 主幹) 所連接的網際網路電話語音服務提供者 (SBC)  (的會話邊界控制器
    
    <div>
    

    > [!NOTE]  
    > 如果您也部署企業語音，轉送伺服器和 PSTN 閘道是企業語音部署的一部分。 如果您不是部署企業語音，您必須至少部署一個轉送伺服器，以及至少一個 PSTN 閘道、IP-PBX 或 SBC 用於電話撥入式會議。

    
    </div>

  - **檔存放區**    檔存放區用於記錄的名稱音訊檔。 檔存放區是每個 Enterprise Edition 或 Standard Edition 部署中的標準元件。

  - **使用者存放區**    使用者存放區用於儲存使用者 Lync Server 2013 Pin。 會散列 Pin。 在每個 Enterprise Edition 或 Standard Edition 部署中，使用者存放區是一個標準元件。

  - **Lync Server 控制台**    使用 Lync Server 控制台可以設定某些撥入設定。

  - **Lync Server 管理命令**     介面您可以使用 Lync Server 管理命令介面 Cmdlet 來設定所有撥入設定。 Lync Server 管理命令介面 Cmdlet 可用於部署、設定、執行、監控會議應答應用程式和會議宣告應用程式，以及進行疑難排解。 如需特定 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。

</div>

<div>

## <a name="supported-topologies"></a>支援的拓撲

在 Lync Server 2013 中，執行會議服務的伺服器一定會組合前端伺服器或 Standard Edition server。 在初始部署期間，拓撲產生器可讓您選擇在拓撲中包含會議。 您也可以使用拓撲產生器，將會議新增至現有的部署。 如需詳細資訊，請參閱 [在 Lync Server 2013 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。

<div>

## <a name="dial-in-conferencing-toplogies"></a>電話撥入式會議 Toplogies

您可以在下列拓撲和設定中部署電話撥入式會議：

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

  - 有或沒有 Enterprise Voice

您可以在中央網站部署應用程式服務、會議應答應用程式和會議宣告應用程式，但不能在分支網站中。

<div>


> [!NOTE]  
> 如果您部署電話撥入式會議，則必須在每個部署 Lync Server 2013 會議的集區中部署它。 您不需要在每個集區中指派存取號碼，但是您必須在每個集區中部署電話撥入式會議功能。 當使用者呼叫一個集區中的存取號碼，以在不同的集區加入 Lync Server 2013 會議時，此需求即支援記錄的名稱功能。



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a>Lync Server 2013 和 Office Web Apps 支援的拓撲

Lync Server 2013 提供下列方式來設定 Office Web Apps Server。 視您的需求而定，您可以：

  - **在您組織的防火牆之後和相同的網路區域中，安裝 Lync Server 2013 和 Office Web Apps Server 內部部署。** 透過此拓撲，將會透過您的反向 proxy 伺服器提供外部存取的 Office Web Apps Server。 [Lync Server 2013] 和 [Office Web Apps Server (] 或 [Office Web Apps Server 伺服器陣列]) 都會安裝在內部部署及組織防火牆之後。 理想狀況下，您應將 Office Web Apps Server 安裝在與 Lync Server 相同的網路區域中。
    
    外部 Lync 用戶端可以使用反向 proxy 伺服器連線至 Lync Server 2013 和 Office Web Apps Server，這是一部伺服器，用來自網際網路的要求，並將它們轉寄給內部網路。  (內部用戶端不需要使用反向 proxy 伺服器，因為他們可以直接連線到 Office Web Apps Server。如果您想要使用僅供 Lync Server 2013 使用的專用 Office Web Apps Server 伺服器陣列，則 ) 此拓撲最適合運作。

  - **使用外部部署的 Office Web Apps Server**
    
    在此拓撲中，會在內部部署 Lync Server 2013，並使用在 Lync Server 網路區域以外部署的 Office Web Apps Server。 如果 Office Web Apps Server 在公司中的多個應用程式之間共用，而且部署在需要 Lync 伺服器以使用 Office Web Apps Server 的外部介面的網路中，則可能會發生這種情況，反之亦然。
    
    您不需要安裝反向 proxy 伺服器;相反地，Office Web Apps Server 對 Lync Server 2013 的所有要求都是透過您的 Edge Server 路由傳送。 您的內部和外部 Lync 用戶端會使用外部 URL 連線到 Office Web Apps Server。
    
    如果 Office Web Apps Server 部署在您的內部防火牆外，請選取 [ **Office Web Apps server] 部署在拓撲產生器中的外部網路 (，也就是周邊/網際網路) ** 。 如需詳細資訊，請參閱設定 [Office Web Apps Server 和 Lync Server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

不論您選取的拓撲為何，開啟正確的防火牆埠都很重要。 您必須確定在 Office Web Apps Server、負載平衡器或 Lync Server 上，防火牆沒有封鎖 DNS 名稱、IP 位址和埠。

<div>


> [!NOTE]  
> 提供 Office Web Apps Server 外部存取的另一個選項是在周邊網路中部署伺服器。 如果您選擇執行這項操作，請記住，Office Web Apps Server 安裝程式需要伺服器電腦成為您的 Active Directory 網域的成員。 除非您的網路原則允許周邊網路中的電腦成為 Active Directory 網域成員，否則建議您不要在周邊網路中安裝 Office Web Apps Server。 相反地，您應該在內部網路上安裝 Office Web Apps Server，並透過反向 proxy 伺服器提供外部使用者存取。



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

