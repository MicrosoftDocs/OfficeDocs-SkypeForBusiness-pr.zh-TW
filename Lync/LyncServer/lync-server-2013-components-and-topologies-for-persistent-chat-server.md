---
title: Lync Server 2013：持久聊天伺服器的元件與拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14ae22b2afed27109fb6e2c514211293cef42a46
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 中持續聊天伺服器的元件與拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

持續聊天伺服器支援單伺服器設定和多重伺服器設定。 永久聊天伺服器也可以在 Lync Server 2013 標準版伺服器上執行。 這些設定包含下列持續性聊天伺服器元件與拓撲。

<div>

## <a name="persistent-chat-server-components"></a>持續聊天伺服器元件

安裝最新版本的持久性聊天伺服器需要下列元件：

  - 一或多台執行持續聊天伺服器且提供下列服務的電腦：
    
      - 持續聊天服務
    
      - 相容性服務，在啟用合規性時開啟
    
    <div>
    

    > [!IMPORTANT]  
    > 在 Lync Server 2013 中，[檔案上傳/下載] 的持續聊天 Web 服務現在已 collocated Lync&nbsp;server 2013 前端伺服器。<BR>Lync Server 2013&nbsp;前端伺服器也會 Collocated 聊天室管理的持續聊天 Web 服務。

    
    </div>

  - 伺服器（如果使用的是多個伺服器的話），該主機會主持 SQL Server 後端資料庫，以託管 [聊天室內容]、[會議室] 和 [類別] 的 [永久聊天] 內容資料庫。
    
    <div>
    

    > [!NOTE]  
    > 後端資料庫會儲存聊天記錄資料，包括所建立之類別和持續聊天室的相關資訊。

    
    </div>

  - 如果已啟用合規性，就會儲存一個伺服器（如果使用鏡像的話的話），宿主 SQL Server 後端資料庫以託管持續聊天相容性資料庫，且會儲存合規性事件和聊天內容。

若要從個別的電腦（例如系統管理主控台）管理持久聊天伺服器，請使用電腦上的 Lync Server [控制台]。 這個電腦必須接著部署在 Active Directory 網域服務網域中，在林根中至少有一個通用類別目錄伺服器。

如需持續性聊天伺服器的硬體和軟體需求的詳細資訊，請參閱在支援檔中的 lync server [2013 支援的永久性聊天伺服器技術需求](lync-server-2013-technical-requirements-for-persistent-chat-server.md)、 [lync server 2013 支援的硬體](lync-server-2013-supported-hardware.md)，以及[Lync server 2013 中的伺服器軟體和基礎結構支援](lync-server-2013-server-software-and-infrastructure-support.md)。

</div>

<div>

## <a name="supported-collocation"></a>支援的 Collocation

Lync Server 2013 支援各種不同的 collocation 案例，可讓您靈活地在一部伺服器（如果您有小型組織）上執行多個元件，或在不同的伺服器上執行個別元件（如果您有需要可伸縮性和效能的較大型組織。 在您決定是否要 collocate 元件之前，請務必先考慮伸縮性因素。

如果相容性已啟用，則持久聊天合規性服務會與 Lync Server 2013 前端伺服器 collocated。

永久聊天伺服器可以部署在標準版伺服器上。 在本機 SQL Server Express 後端伺服器的標準版伺服器上，持續式聊天伺服器後端伺服器和持續式聊天合規性資料庫可以 collocated。 如需可在該處 collocated 之元件的詳細資訊，請參閱支援檔中的[Lync server 2013 支援的伺服器 collocation](lync-server-2013-supported-server-collocation.md) 。

在 Lync Server 2013 企業版中，不能在企業版伺服器上 collocated 持久聊天伺服器。 持久聊天伺服器的 SQL Server 資料庫可以與企業版前端池的後端伺服器資料庫 collocated。 您也可以使用企業版池的後端伺服器資料庫，collocated 適用于持續聊天合規性的 SQL Server 資料庫。

<div>


> [!IMPORTANT]  
> 主持持久聊天資料庫的伺服器可以裝載其他資料庫。 不過，當您考慮將持續聊天資料庫與其他資料庫 collocating 時，請注意，如果您要儲存的訊息超過幾個使用者，持久聊天資料庫所需的磁碟空間可能會變得很大。 基於這個原因，我們不建議您 collocating 與後端資料庫的持續聊天資料庫。



</div>

如果您 collocate 與後端資料庫的持續聊天資料庫，您可以針對任何或所有資料庫使用單一的 SQL Server 實例，或者，您也可以針對每個資料庫使用單獨的 sql Server 實例，但有下列限制：

  - 每個 SQL Server 實例都只能包含一個後端資料庫及單一持久聊天資料庫。

如需 collocation 所有伺服器角色和資料庫的詳細資料，請參閱可支援檔中的[Lync server 2013 支援的伺服器 collocation](lync-server-2013-supported-server-collocation.md) 。

</div>

<div>

## <a name="persistent-chat-server-topologies"></a>持續聊天伺服器拓撲

持續聊天伺服器支援下列拓撲：

  - Lync Server 2013 企業版單一伺服器持久聊天伺服器前端伺服器

  - Lync Server 2013 企業版多個伺服器持續聊天伺服器前端伺服器

  - 使用 SQL Server Express 的 Lync Server 2013 標準版伺服器

  - Lync Server 2013 標準版伺服器以及在個別伺服器上使用標準版伺服器作為下一個躍點伺服器的持久聊天伺服器。

您可以使用 [拓撲建立器]，將持續性聊天伺服器新增到 Lync Server 2013 部署。 您可以將單一伺服器或多個伺服器持續聊天伺服器池新增到您的拓撲。

<div>


> [!IMPORTANT]  
> 使用 [拓撲建立器] 建立單一伺服器的持續聊天伺服器池之後，您就無法將其他伺服器新增到該池中。



</div>

<div>

## <a name="single-server-topology"></a>單伺服器拓朴

持續聊天伺服器的最小設定和最簡單的部署是單一持續式聊天伺服器前端伺服器拓撲。 此部署需要單一伺服器來執行持續聊天伺服器（如果相容性已啟用，也可選擇執行合規性服務）、託管 SQL Server 資料庫的伺服器，以及如果需要合規性，則是 SQL Server 資料庫來儲存合規性資料。

<div>


> [!IMPORTANT]  
> 您無法將其他伺服器新增至永久聊天伺服器池中，該池是在拓撲建立器中以單一伺服器部署的形式啟動。 我們建議您使用多重伺服器池拓撲結構，即使您使用的是單一伺服器，您也可以在日後新增更多伺服器（如果需要的話）。



</div>

下圖顯示單一持續聊天伺服器前端伺服器（符合合規性）的所有必要和選用元件。

**單一持久聊天伺服器**

![單一伺服器拓朴與合規性服務](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "單一伺服器拓撲（含合規性服務")）

</div>

<div>

## <a name="multiple-server-topology"></a>多重伺服器拓朴

若要提供更大的容量及可靠性，您可以部署多伺服器拓朴，如在[Lync server 2013 規劃持續聊天伺服器中](lync-server-2013-planning-for-persistent-chat-server.md)所述。 多重伺服器拓朴可包含多達四個執行持續聊天伺服器的活動電腦（高可用性和災害復原設定允許最多八個，但只有四個作用中的4個作用中，還有四個作用中的四個）。 每個伺服器可支援多達20000並行的使用者，總共是連線到具有4個伺服器的持久聊天伺服器池中的80000個併發使用者。 多重伺服器拓朴與單一伺服器拓朴一樣，只是多個伺服器主機持久的聊天伺服器，而且可以擴大規模。 多台執行持續聊天伺服器的電腦應該位於與 Lync Server 和合規性服務相同的 Active Directory 網域服務網域中。

下圖顯示多伺服器拓朴中的所有元件，其中多台電腦執行持續聊天伺服器、選用規範服務，以及個別的合規性資料庫。

**多個持續聊天伺服器**

![多個伺服器拓撲]結構(images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "多個伺服器拓撲")

多伺服器拓朴提供伺服器功能的彙集。 在伺服器池中，持續聊天服務會與資料進行通訊和共用。 例如，您可以從系統中的任何持續聊天服務取得最初張貼到一個持續聊天服務的聊天記錄。 透過一個持久聊天服務上傳的檔案，可透過任何持續聊天服務存取。 使用者可以連線至不同的持續聊天伺服器前端伺服器，而且可以彼此聊天和通訊。

TCP 8011 的預設埠會將伺服器連線到伺服器池中，且持續聊天服務會使用它來溝通本身，或用於管理目的。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

