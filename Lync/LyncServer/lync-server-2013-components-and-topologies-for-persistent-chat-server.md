---
title: Lync Server 2013： Persistent Chat Server 的元件和拓撲
description: Lync Server 2013： Persistent Chat Server 的元件和拓撲。
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
ms.openlocfilehash: 937b3d6f2716d9471e61cffd651847f6de9d83f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576809"
---
# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 中持久聊天伺服器的元件和拓撲

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

Persistent Chat Server 同時支援單一伺服器設定和多部伺服器設定。 Persistent Chat Server 也可以在 Lync Server 2013 Standard Edition Server 上執行。 這些設定包含下列 Persistent Chat Server 元件和拓撲。

<div>

## <a name="persistent-chat-server-components"></a>Persistent Chat Server 元件

安裝最新版本的 Persistent Chat Server 需要下列元件：

  - 一或多部執行 Persistent Chat Server 的電腦，並提供下列服務：
    
      - Persistent Chat service
    
      - 規範服務，會在啟用規範時開啟
    
    <div>
    

    > [!IMPORTANT]  
    > 在 Lync Server 2013 中，檔案上傳/下載的 Persistent Chat Web 服務現在已與 Lync Server 2013 &nbsp; 前端伺服器組合。<BR>聊天室管理的 Persistent Chat Web 服務也會與 Lync Server 2013 &nbsp; 前端伺服器組合。

    
    </div>

  - 如果) 使用鏡像，則伺服器 (s) 會 (多部伺服器，該主機會主控 SQL Server 後端資料庫，以裝載存放聊天室內容、會議室和類別的持久聊天內容資料庫。
    
    <div>
    

    > [!NOTE]  
    > 後端資料庫會儲存聊天記錄資料，包括所建立之類別和持續聊天室的資訊。

    
    </div>

  - 如果已啟用相容性，則伺服器 (s) 會 (多部伺服器。如果) 使用鏡像，則會主控 SQL Server 後端資料庫，以主控持久的聊天室規範資料庫，以儲存相容性事件和聊天內容的目的。

若要從不同的電腦管理 Persistent Chat Server (例如管理主控台) ，請使用電腦上的 Lync Server 控制台。 這部電腦必須部署在 Active Directory 網域服務網域中，至少要有一個樹系根中的通用類別目錄伺服器。

如需有關 Persistent Chat Server 的硬體和軟體需求的詳細資訊，請參閱支援檔中的 lync server [2013 中的 [Persistent Chat server] 的技術需求](lync-server-2013-technical-requirements-for-persistent-chat-server.md)（lync server [2013 支援的硬體](lync-server-2013-supported-hardware.md)，以及 [Lync server 2013 中的伺服器軟體和基礎結構支援](lync-server-2013-server-software-and-infrastructure-support.md) ）。

</div>

<div>

## <a name="supported-collocation"></a>支援的組合

Lync Server 2013 支援各種組合案例，可讓您靈活地在一部伺服器 (上執行多個元件，以節省硬體成本，如果您有小型組織) ，或是在不同的伺服器上執行個別元件 (如果您有較大的組織需要可擴充性和效能) 。 在您決定是否組合元件之前，務必考量延展性因素。

如果啟用規範，則 Persistent Chat 合規性服務會與 Lync Server 2013 前端伺服器進行組合。

Persistent Chat Server 可以部署在 Standard Edition server 上。 在本機 SQL Server Express 後端伺服器上的 Standard Edition server 上，可以組合持久的 Chat Server 後端伺服器和 Persistent 聊天室規範資料庫。 如需可在該處組合之元件的詳細資訊，請參閱支援檔中的 [支援的伺服器組合（Lync server 2013](lync-server-2013-supported-server-collocation.md) ）。

對於 Lync Server 2013 Enterprise Edition，無法在 Enterprise Edition Server 上組合 Persistent Chat server。 Persistent Chat Server 的 SQL Server 資料庫可與 Enterprise Edition 前端集區的後端伺服器資料庫組合。 使用 Enterprise Edition 集區的後端伺服器資料庫也可以組合適用于持續性聊天規範的 SQL Server 資料庫。

<div>


> [!IMPORTANT]  
> 主控 Persistent Chat 資料庫的伺服器可以主控其他資料庫。 不過，當您考慮將 Persistent Chat 資料庫與其他資料庫組合時，請注意，如果您儲存的是少數幾個使用者的郵件，則 Persistent Chat 資料庫所需的磁碟空間會變得非常大。 基於這個理由，我們不建議組合 Persistent Chat 資料庫與後端資料庫。



</div>

如果您使用後端資料庫組合 Persistent Chat 資料庫，您可以針對任何或所有資料庫使用單一的 SQL Server 實例，也可以針對每個資料庫使用不同的 SQL Server 實例，但有下列限制：

  - 每個 SQL Server 實例只能包含單一後端資料庫和單一持久聊天資料庫。

如需組合的所有伺服器角色及資料庫的詳細資訊，請參閱支援檔中的 [Lync server 2013 中的支援伺服器組合](lync-server-2013-supported-server-collocation.md) 。

</div>

<div>

## <a name="persistent-chat-server-topologies"></a>Persistent Chat Server 拓撲

Persistent Chat Server 支援下列拓撲：

  - Lync Server 2013 Enterprise Edition single server Persistent Chat server 前端伺服器

  - Lync Server 2013 Enterprise Edition 多部伺服器 Persistent Chat Server 前端伺服器

  - 使用 SQL Server Express 的 Lync Server 2013 Standard Edition Server

  - 使用 Standard Edition server 做為下一個躍點伺服器的不同伺服器上的 Lync Server 2013 Standard Edition server 和 Persistent Chat Server。

您可以使用拓撲產生器，將 Persistent Chat Server 新增至 Lync Server 2013 部署。 您可以將單一伺服器或多部伺服器的持久聊天伺服器集區新增至您的拓撲。

<div>


> [!IMPORTANT]  
> 使用拓撲產生器建立持久聊天伺服器集區和單一伺服器之後，就無法將其他伺服器新增至集區。



</div>

<div>

## <a name="single-server-topology"></a>單一伺服器拓撲

Persistent Chat Server 的最小設定和最簡單部署是單一持久聊天伺服器前端伺服器拓撲。 此部署需要執行 Persistent Chat Server (的單一伺服器，如果符合性已啟用) 、主控 SQL Server 資料庫的伺服器及相容性（若有必要），則會執行該程式，以儲存相容性資料。

<div>


> [!IMPORTANT]  
> 您無法將其他伺服器新增至 Persistent Chat Server 集區，此集區在拓撲產生器中以單一伺服器部署的方式啟動。 即使您正在使用單一伺服器，我們仍建議您使用多伺服器集區拓撲，這樣您就可以在日後視需要新增更多的伺服器。



</div>

下圖顯示單一 Persistent Chat Server 前端伺服器及規範的拓撲的所有必要和選用元件。

**單一常設聊天室伺服器**

![具有規範服務的單一伺服器拓撲](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "具有規範服務的單一伺服器拓撲")

</div>

<div>

## <a name="multiple-server-topology"></a>多部伺服器拓撲

若要提供更大的容量與可靠性，您可以部署多伺服器拓撲，如在 [Lync server 2013 中規劃 Persistent Chat server](lync-server-2013-planning-for-persistent-chat-server.md)所述。 多重伺服器拓撲可包含多達四部使用中持久聊天伺服器的使用中電腦 (高可用性和嚴重損壞修復設定允許最多八個，但只有四個可以使用中，而在待機) 仍可使用。 每一部伺服器最多可支援20000並行使用者，共連接至具有4部伺服器的持久聊天伺服器集區的併發使用者總數為80000。 多伺服器拓撲與單一伺服器拓撲相同，只是多部伺服器主控 Persistent Chat Server，而且可以擴充更高。 多部執行 Persistent Chat Server 的電腦應該位於與 Lync Server 和合規性服務相同的 Active Directory 網域服務網域中。

下圖顯示多部伺服器拓撲的所有元件，包含多部執行 Persistent Chat Server 的電腦、選用的規範服務和個別的規範資料庫。

**多部常設聊天室伺服器**

![多部伺服器拓撲](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "多部伺服器拓撲")

多伺服器拓撲提供伺服器功能的集區。 在伺服器集區中，Persistent Chat service 會通訊和共用資料。 例如，您可以從系統中的任何 Persistent Chat service 取得最初發佈到某項 Persistent Chat service 的聊天記錄。 任何 Persistent chat service 都可以存取透過某項 Persistent Chat service 上傳的檔案。 使用者可以連線至不同的持久聊天伺服器前端伺服器，也可以相互聊天和通訊。

TCP 8011 的預設埠會將伺服器連線至伺服器集區，而 Persistent Chat service 會使用該埠自行進行通訊，或用於管理目的。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

