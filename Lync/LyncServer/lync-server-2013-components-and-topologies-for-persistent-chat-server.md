---
title: Lync Server 2013： 的元件和拓撲 Persistent Chat Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be9ab539b652fc1d6ae82883df1f8875a0257614
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a>Persistent Chat Server in Lync Server 2013 的元件和拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-05_

Persistent Chat Server 支援單一伺服器組態和多部伺服器組態。 Persistent Chat Server 也可以在 Lync Server 2013 Standard Edition server 上執行。 這些設定包括下列 Persistent Chat Server 元件和拓撲。

<div>

## <a name="persistent-chat-server-components"></a>常設聊天室伺服器元件

安裝最新版的 Persistent Chat Server 需要下列元件：

  - 一或多個電腦執行 Persistent Chat Server，並提供下列服務：
    
      - 常設聊天服務
    
      - 規範服務，會在啟用規範時開啟
    
    <div>
    

    > [!IMPORTANT]  
    > 在 Lync Server 2013 常設聊天室 Web 服務的檔案上傳/下載中現在已組合搭配 Lync Server 2013&nbsp;前端伺服器。<BR>常設聊天室 Web 服務用於聊天室管理也組合搭配 Lync Server 2013&nbsp;前端伺服器。

    
    </div>

  - 伺服器 （多部用於一部伺服器如果鏡像） 裝載 SQL Server 後端資料庫，以裝載儲存聊天室內容、 房間和類別的常設聊天室內容資料庫。
    
    <div>
    

    > [!NOTE]  
    > 後端資料庫可儲存交談記錄資料，包括類別和所建立的常設聊天室的資訊。

    
    </div>

  - 如果啟用規範，裝載 SQL Server 後端資料庫，以裝載儲存規範事件與交談內容，基於規範目的常設聊天室規範資料庫伺服器 （多部用如果鏡像的一部伺服器）。

若要管理 Persistent Chat Server 從不同的電腦 （例如系統管理主控台），請在電腦上使用 Lync Server Control Panel。 這部電腦然後必須部署在 Active Directory 網域服務的網域中,，但會與樹系根中至少一個通用類別目錄伺服器。

如需 for Persistent Chat Server 的硬體和軟體需求的詳細資訊，請參閱支援文件中[的 Technical requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md)、 [Lync Server 2013 支援硬體](lync-server-2013-supported-hardware.md)，和[Lync Server 2013 中的伺服器軟體和基礎結構支援](lync-server-2013-server-software-and-infrastructure-support.md)。

</div>

<div>

## <a name="supported-collocation"></a>支援的組合

Lync Server 2013 支援的各種組合案例中，提供的彈性來節省硬體成本 （如果您擁有小型組織） 的一部伺服器，執行多個元件，或在不同的伺服器上執行個別元件 (如果您有大型組織需要延展性和效能）。 在您決定是否組合元件之前，務必考量延展性因素。

常設聊天室規範服務，如果啟用規範，則已組合與 Lync Server 2013 前端伺服器中。

Persistent Chat Server 可以部署在 Standard Edition server 上。 常設聊天室伺服器後端伺服器和常設聊天室規範資料庫可以組合在 Standard Edition 伺服器的本機 SQL Server Express 後端伺服器上。 如需可以那里組合的元件的詳細資訊，請參閱支援文件中的[Lync Server 2013 中的支援伺服器共同配置](lync-server-2013-supported-server-collocation.md)。

針對 Lync Server 2013 Enterprise Edition，常設聊天室伺服器無法配置在一起 Enterprise Edition 伺服器上。 Persistent Chat Server 的 SQL Server 資料庫可以與 Enterprise Edition 前端集區的後端伺服器資料庫組合。 常設聊天室規範 SQL Server 資料庫也可以組合與 Enterprise Edition 集區的後端伺服器資料庫。

<div>


> [!IMPORTANT]  
> 常設聊天室資料庫所在的伺服器可以主控其他資料庫。 不過，當您考慮組合常設聊天室資料庫與其他資料庫，請注意，如果您儲存多個使用者的郵件的磁碟空間需要常設聊天室資料庫可以變得非常大。 基於這個理由，我們不建議組合常設聊天室資料庫與後端資料庫。



</div>

如果您在組合常設聊天室資料庫與後端資料庫，您也可以使用任何的 SQL Server 的單一執行個體或所有資料庫，或者您都可以使用 SQL Server 個別執行個體的每個資料庫，但有以下限制：

  - 每個 SQL Server 執行個體可以包含單一後端資料庫和單一常設聊天室資料庫。

如需所有伺服器角色和資料庫組合的詳細資訊，請參閱支援文件中的[Lync Server 2013 中的支援伺服器共同配置](lync-server-2013-supported-server-collocation.md)。

</div>

<div>

## <a name="persistent-chat-server-topologies"></a>常設聊天室伺服器拓撲

Persistent Chat Server 支援下列拓撲：

  - Lync Server 2013 Enterprise Edition 單一伺服器 Persistent Chat Server 前端伺服器

  - Lync Server 2013 Enterprise Edition 多部伺服器 Persistent Chat Server 前端伺服器

  - 使用 SQL Server Express 的 Lync Server 2013 Standard Edition server

  - Lync Server 2013 Standard Edition server 和使用 Standard Edition server 的下一個躍點伺服器為一部伺服器上的 Persistent Chat Server。

您可以使用拓撲產生器，將 Persistent Chat Server 新增至 Lync Server 2013 部署。 您可以新增單一或多個伺服器 Persistent Chat Server 集區至您的拓撲。

<div>


> [!IMPORTANT]  
> 您使用拓撲產生器來建立含有單一伺服器 Persistent Chat Server 集區之後，您無法新增其他伺服器至集區。



</div>

<div>

## <a name="single-server-topology"></a>單一伺服器拓撲

最小的設定資料庫和 for Persistent Chat Server 的最簡單部署是單一常設聊天室伺服器前端伺服器的拓撲。 此部署需要執行常設聊天室伺服器 （如果啟用規範，選擇性地執行規範服務，）、 主控這兩個 SQL Server 資料庫伺服器的單一伺服器和合規性是否有需要，要儲存的 SQL Server 資料庫規範資料。

<div>


> [!IMPORTANT]  
> 您無法新增其他伺服器至已啟動拓撲產生器中的單一伺服器部署為 Persistent Chat Server 集區。 即使您正在使用單一伺服器，我們仍建議您使用多伺服器集區拓撲，這樣您就可以在日後視需要新增更多的伺服器。



</div>

下圖顯示內含規範單一常設聊天室伺服器前端伺服器拓撲的所有必要與選用元件。

**單一常設聊天室伺服器**

![具有規範服務的單一伺服器拓撲](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "具有規範服務的單一伺服器拓撲")

</div>

<div>

## <a name="multiple-server-topology"></a>多部伺服器拓撲

若要提供更大的容量及可靠性，您可以部署多部伺服器拓撲，[規劃 Persistent Chat Server in Lync Server 2013 ](lync-server-2013-planning-for-persistent-chat-server.md)中所述。 多部伺服器拓撲可以包含多達四個作用中的電腦執行 Persistent Chat Server （高可用性和災害復原設定會允許最多第八個，但只有四個可以是作用中，其餘四處於待命狀態）。 每個伺服器可支援多達 20000 位並行使用者，總共為 80000 位並行使用者連線到具有 4 部伺服器 Persistent Chat Server 集區。 在多部伺服器拓撲是單一伺服器拓撲相同之處在於多部伺服器主控 Persistent Chat Server，並可將其調整更高版本。 執行 Persistent Chat Server 的多部電腦應該位於相同的 Active Directory 網域服務網域 Lync 伺服器和規範服務。

下圖顯示所有的元件的多部伺服器拓撲與執行 Persistent Chat Server、 選用的 Compliance service 和獨立的規範資料庫的多部電腦。

**多部常設聊天室伺服器**

![多伺服器拓撲](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "多伺服器拓撲")

多伺服器拓撲提供伺服器功能的集區。 伺服器集區中的常設聊天室服務通訊，並共用資料。 例如，原本已張貼到一個常設聊天室服務的聊天歷程記錄系統中是可從任何常設聊天室服務。 任何的常設聊天室服務可透過一個常設聊天室服務上傳的檔案。 使用者可以連線至不同 Persistent Chat Server 前端伺服器和可以聊天並與彼此進行通訊。

預設連接埠 TCP 8011 會將伺服器連接至伺服器集區，並由通訊之間，或系統管理用途的常設聊天室服務。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

