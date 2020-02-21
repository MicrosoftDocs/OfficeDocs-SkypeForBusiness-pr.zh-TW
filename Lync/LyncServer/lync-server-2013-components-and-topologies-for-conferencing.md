---
title: 會議的 Lync Server 2013 元件和拓撲
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
ms.openlocfilehash: e4c843bbe5c34aaf0ad98ca73e8ebd33820b87d2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的會議的元件和拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-04_

當您在拓撲產生器] 中選取會議時，會議部署為前端伺服器或 Standard Edition server 的一部分。 電話撥入式會議和 PowerPoint 共用需要額外的元件和設定。 下列各節說明支援的元件和拓撲 web 會議、 A / V 會議及電話撥入式會議。

<div>

## <a name="supported-components"></a>支援的元件

元件只有 web 會議和 A / V 會議要求是貴組織的前端伺服器或 Standard Edition 伺服器。 前端伺服器和 Standard Edition server 的硬體和軟體需求清單，請參閱[支援 Lync Server 2013 的](lync-server-2013-supported-hardware.md)軟硬體[的 Server software and Lync Server 2013 中支援的基礎結構](lync-server-2013-server-software-and-infrastructure-support.md)。

Lync Server 2013 使用 Office Web Apps 與 Office Web Apps Server 來處理共用和 PowerPoint 簡報的轉譯。 如需安裝及設定 Office Web Apps Server 的詳細資訊，請參閱[設定整合 Office Web Apps Server 與 Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

除了需求為 web 會議和 A / V 會議、 電話撥入式會議使用下列的 Lync Server 2013 元件：

  - **應用程式服務**   應用程式服務提供的平台的部署，裝載，及管理整合通訊 (UC) 應用程式。 電話撥入式會議使用兩個需要應用程式服務的 UC 應用程式： 會議服務員和會議宣告服務。 應用程式服務已安裝並啟用每個前端伺服器上的前端集區中，每個 Standard Edition server 上的預設，當您部署會議工作負載，並選取撥入式會議選項。

  - **會議服務員應用程式**   會議服務員應用程式是可接受公用交換的電話網路 (PSTN) 來電、 播放提示，以及聯結的呼叫的整合的通訊應用程式 / V 會議。 會議服務員應用程式已安裝並啟用根據預設，當您部署會議工作負載，並選取撥入式會議選項。

  - **會議宣告應用程式**   會議宣告應用程式是整合的通訊應用程式，會播放撥號音，並提示上執行某些動作 PSTN 參與者、 當參與者加入或離開會議，例如參與者都設為靜音或解除靜音、 某人輸入會議大廳，或會議已鎖定或解除鎖定。 會議宣告應用程式也支援從電話鍵台複頻式訊號 (DTMF) 命令。 會議宣告應用程式會自動安裝及啟動依預設，當您部署會議工作負載，並選取撥入式會議選項。

  - **電話撥入式會議設定] 頁面上**   電話撥入式會議設定 」 頁面會顯示會議撥入號碼與其可用的語言，指派會議資訊 (也就是不需要排定的會議)，在會議 DTMF 控制項，並支援管理個人識別碼 (PIN) 和指派的會議資訊。 [電話撥入式會議設定] 頁面上會自動安裝 Web 服務的一部分。

  - **Lync Server 2013、 中繼伺服器和 PSTN 閘道**   撥入式會議需要 Lync Server 2013 和 PSTN 閘道，與 PSTN 閘道之間翻譯訊號及媒體中繼伺服器和 PSTN 閘道之間的翻譯訊號的中繼伺服器 （和媒體上的，在某些組態中）。 電話撥入式會議，您必須部署至少一部中繼伺服器和至少其中一個下列：
    
      - PSTN 閘道
    
      - IP PBX
    
      - 工作階段界限控制器 (SBC) （適用於網際網路電話語音服務提供者您藉由設定 SIP 主幹連接）
    
    <div>
    

    > [!NOTE]  
    > 如果您也要部署 Enterprise Voice，中繼伺服器和 PSTN 閘道屬於 Enterprise Voice 部署。 如果您不部署 Enterprise Voice，您需要針對撥入式會議部署至少一部中繼伺服器和至少一個 PSTN 閘道、 IP-PBX 或 SBC。

    
    </div>

  - **檔案存放區**   檔案存放區用於記錄名稱音訊檔案。 檔案存放區是每個 Enterprise Edition 或 Standard Edition 部署中的標準元件。

  - **使用者存放區**   使用者存放區用來儲存使用者 Lync Server 2013 的 pin 碼。 Pin 碼都會雜湊。 使用者存放區是每個 Enterprise Edition 或 Standard Edition 部署中的標準元件。

  - **Lync Server Control Panel**   某些撥號對應表設定可以設定使用 Lync Server Control Panel。

  - **Lync Server 管理命令介面**   所有電話撥入式可以設定使用 Lync Server 管理命令介面指令程式。 Lync Server 管理命令介面指令程式可供部署、 設定、 執行、 監視和疑難排解會議服務員應用程式和會議宣告應用程式。 如需特定 cmdlet 的詳細資訊，請參閱 < Lync Server 管理命令介面文件。

</div>

<div>

## <a name="supported-topologies"></a>支援的拓撲

在 Lync Server 2013 中，執行會議服務之伺服器一律與前端伺服器或 Standard Edition server 組合。 在您初始部署期間拓撲產生器] 讓您選擇来包含在您的拓撲中的會議。 您也可以使用拓撲產生器將會議新增至現有的部署。 如需詳細資訊，請參閱[定義和設定 Lync Server 2013 中的拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。

<div>

## <a name="dial-in-conferencing-toplogies"></a>撥入式會議拓撲

您可以部署電話撥入式會議中的下列拓撲和設定：

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

  - 包含或不含 Enterprise Voice

您可以部署應用程式服務、 會議服務員應用程式和會議宣告應用程式在中央網站，但不是在分支網站。

<div>


> [!NOTE]  
> 如果您部署電話撥入式會議，您必須將它部署中部署 Lync Server 2013 會議每個集區。 您不需要指派存取號碼，在每個集區，但您必須部署中每個集區的撥入式會議功能。 這項要求支援錄製的名稱 」 功能，當使用者從一個集區加入 Lync Server 2013 會議的不同的集區中呼叫的存取號碼。



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a>支援的 Lync Server 2013 和 Office Web Apps 的拓撲

Lync Server 2013 提供下列方法來設定 Office Web Apps Server。 您可以根據您的需求：

  - **安裝 Lync Server 2013 與 Office Web Apps Server 內部部署組織的防火牆後面，並位於相同的網路地區。** 與此拓撲中，將透過您的反向 proxy 伺服器提供 Office Web Apps Server 的外部存取。 同時 Lync Server 2013 和 Office Web Apps Server 安裝 （或 Office Web Apps Server 伺服器陣列） 會在內部和貴組織的防火牆後方。 理想狀況下，您應該在 Lync Server 位於相同網路地區中安裝 Office Web Apps Server。
    
    外部的 Lync 用戶端可以將使用反向 proxy 伺服器，也就是會接受來自網際網路的要求，並將其轉寄至內部網路的伺服器連線到 Lync Server 2013 以及 Office Web Apps Server。 （內部用戶端不需要使用反向 proxy 伺服器，因為他們可以直接連線至 Office Web Apps Server）。如果您想要使用專用的 Office Web Apps Server 伺服器陣列只使用 Lync Server 2013，這種拓撲的效果最佳。

  - **使用外部部署的 Office Web Apps Server**
    
    在此拓撲中，Lync Server 2013 內部部署，且使用 Lync Server 網路區域外部署 Office Web Apps Server。 當 Office Web Apps Server 跨公司內的多個應用程式共用，並需要 Lync Server 以使用 Office Web Apps server，反之亦然的外部介面的網路中部署可能發生這種情形。
    
    您不需要安裝的反向 proxy 伺服器;相反地，會透過 Edge Server 路由傳送的所有要求與 Office Web Apps Server 到 Lync Server 2013。 您的內部和外部的 Lync 用戶端連線至 Office Web Apps Server 使用的外部 URL。
    
    如果 Office Web Apps Server 部署在內部防火牆外，然後選取 [ **Office Web Apps Server 部署在外部網路 （亦即周邊/網際網路）** ] 選項，在拓撲產生器。 如需詳細資訊請參閱[設定整合 Office Web Apps Server 與 Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

不論您選擇的拓撲，很重要，開啟正確的防火牆連接埠。 您必須確定的 DNS 名稱、 IP 位址和連接埠不被防火牆封鎖 Office Web Apps Server、 負載平衡器或 Lync Server 上。

<div>


> [!NOTE]  
> Office Web Apps Server 來提供外部存取的另一個選項是部署在周邊網路中的伺服器。 如果您選擇若要這麼做，請記住，Office Web Apps Server 安裝程式需要伺服器電腦是 Active Directory 網域的成員。 除非您的網路原則允許在周邊網路 Active Directory 網域成員電腦，否則建議您不要在周邊網路中安裝 Office Web Apps Server。 相反地，您應該在內部網路中安裝 Office Web Apps Server，並提供透過反向 proxy 伺服器的外部使用者存取。



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

