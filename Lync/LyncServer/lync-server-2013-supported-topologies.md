---
title: Lync Server 2013 支援的拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f200cde348d1fbdc931daa25abef28aec804a1b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-topologies-in-lync-server-2013"></a>Lync Server 2013 中支援的拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-01-14_

Lync Server 2013 支援部署組織內部部署的網站，並與 Lync Online 部署（稱為混合式部署）整合內部部署部署。 在混合式部署中，有些使用者是駐留在內部部署的，而某些使用者則是在線上。

針對內部部署的部署，Lync Server 2013 支援部署一或多個可調整以滿足高可用性和位置需求的網站。 您可以建立這些網站及其元件的結構，以符合貴組織的存取和復原需求。

Lync Server 2013 內部部署部署包括下列各項：

  - 您的部署必須包含至少一個中央網站（也稱為「資料中心」）。 每個中央網站都必須包含至少一個企業版的前端池或一個標準版伺服器。 這些內容包括下列各項：
    
      - [企業版頂層端] 池，包含一或多個前端伺服器（通常是至少兩個可伸縮性的前端伺服器）和獨立的後端伺服器。 前端池最多可以包含十二個前端伺服器。 多個前端伺服器需要負載平衡。 針對 SIP 流量，我們建議 DNS 負載平衡，但也支援硬體負載平衡。 如果您使用 [DNS 負載平衡] 進行 SIP 流量，您仍需要用於 HTTP 流量的硬體負載平衡器。 我們建議 SQL Server 鏡像提供高可用性的資料庫。 後端資料庫需要個別的實例，但您可以 collocate 封存資料庫、監視資料庫、持久聊天資料庫，以及與它持久的聊天合規性資料庫。 Lync Server 2013 支援在您部署中的檔案共用中使用共用的群集。 如需資料庫儲存空間需求的詳細資料，請參閱[Lync Server 2013 中的資料庫軟體支援](lync-server-2013-database-software-support.md)。 如需檔案儲存空間需求的詳細資料，請參閱[Lync Server 2013 中的檔案儲存支援](lync-server-2013-file-storage-support.md)。
        
        <div>
        

        > [!IMPORTANT]  
        > 如果您 collocate Lync Server 資料庫，我們強烈建議您評估可能會影響可用性和效能的所有因素。 若要確認容錯移轉功能，建議測試所有容錯移轉案例。

        
        </div>
    
      - 標準版伺服器，包括 collocated SQL Server Express 資料庫。

  - 您的部署也可以有一個或多個與中央網站相關聯的分支網站。

本節說明 Lync Server 2013 部署的網站和元件。 如需有關 Lync Server 2013 網站、拓撲和元件規劃的詳細資料，請參閱規劃 Lync server 2013 以及[Lync server 2013](lync-server-2013-reference-topologies.md)中的 [規劃] 檔中的參考拓撲[前，您必須瞭解的拓撲結構基礎](lync-server-2013-topology-basics-you-must-know-before-planning.md)。 如需整合舊版元件的詳細資訊，請參閱[Lync Server 2013 中支援的遷移路徑和共存案例](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md)。

<div>


> [!NOTE]  
> 前端、邊緣、轉送和控制器伺服器角色不支援延伸池。



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a>中央網站拓撲與元件（內部部署）

雖然中心網站拓朴必須包含一個前端池或一個標準版伺服器，但每個中央網站也可以包含下列專案：

  - 多個前端池，可能位於同一個網域或不同的網域。 不過，前端池中的所有前端伺服器，以及該池的後端伺服器，都必須位於同一個網域中。

  - 多個標準版伺服器。

  - 在 Lync Server 2013 中與 Office Web 應用程式搭配使用的 office Web Apps Server，用來處理 Microsoft PowerPoint 簡報的共用和轉譯。

  - 在周邊網路中的 edge 伺服器或邊緣池，如果您想讓您的部署支援同盟夥伴、公用 IM 連線、可擴展的訊息和目前狀態通訊協定（XMPP）閘道、遠端使用者存取權、參與會議中的匿名使用者，或 Exchange 整合訊息（UM）。 您無法 collocate 任何其他伺服器角色與 Edge 伺服器。 我們建議在適當的地方進行 DNS 負載平衡，但也支援硬體負載平衡。 內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。 您不能在一個 Edge 介面上使用 DNS 負載平衡，而在另一個 Edge 介面上使用硬體負載平衡。 如需負載平衡需求與支援的詳細資訊，請參閱在 lync server 2013 規劃中的[外部使用者存取](lync-server-2013-planning-for-external-user-access.md)在部署檔中的 [規劃檔] 和 [[部署在 lync server 2013 中的外部使用者存取](lync-server-2013-deploying-external-user-access.md)]。

  - 中繼伺服器或池：如果您想要在中央網站的前端池中支援企業語音或電話撥入式會議。 根據您部署企業語音支援的方式，您可以 collocate 前端池中的中繼伺服器（預設）或部署獨立的中繼伺服器或池。 您可以使用 DNS、硬體或應用程式負載平衡（在適當時）從中繼伺服器池的閘道對等發佈流量，包括 PSTN 閘道、IP PBX 或 SIP 中繼會話框線控制（SBC）。如需規劃適當的中繼伺服器拓朴的詳細資料，請參閱規劃檔中的[Lync server 2013 中的中繼伺服器部署指導方針](lync-server-2013-deployment-guidelines-for-mediation-server.md)。

  - 持續聊天伺服器：如果您想要讓使用者能夠參與多方，則會隨時間保留的、以主題為基礎的交談。 若要提供更多容量並增加可靠性，您的拓撲可以包含多部電腦執行持久聊天伺服器。 您無法在企業版池中 collocate 持久聊天伺服器與其他伺服器角色。 不過，您可以在標準版伺服器上 collocate 持續聊天伺服器。 持續聊天需要資料庫，而且如果您實現持久的聊天合規性資料庫，但資料庫可以與存檔資料庫、監視資料庫，或在企業版的後端伺服器上 collocated[前端] 池。 如需規劃適當持久聊天伺服器拓撲的詳細資料，請參閱規劃檔中的[Lync server 2013 中的持續聊天伺服器規劃](lync-server-2013-planning-for-persistent-chat-server.md)。

  - 監控（如果您想要支援音訊/視頻體驗品質（QoE）的資料收集，以及在您的部署中呼叫企業語音和 A/V 會議的詳細資料錄製（CDR）。 您也可以選擇安裝 Microsoft System Center Operations Manager （舊稱 Microsoft 作業管理員），它使用監視 CDR 及 QoE 資料來產生近乎即時的通知，顯示通話可靠性和媒體質量的狀況。 在前端伺服器或標準版伺服器上 collocated [已部署] 時，監視。 [監視] 需要資料庫，但資料庫可以與 [封存資料庫]、[持續聊天資料庫]、[持續聊天規範] 資料庫，或在企業版的 [前端] 池的後端伺服器上 collocated。

  - 如果您想要在您的部署中封存 IM 通訊及會議內容（出於合規性原因），請封存。 當您在前端伺服器或標準版伺服器上進行 collocated 部署時，會進行歸檔。 封存儲存空間需要部署封存資料庫或與 Exchange 2013 儲存區整合。 如果您同時使用兩者（稱為*混合模式*），則 exchange 2013 儲存空間用來儲存託管于 Exchange 2013 的使用者的封存資料，而封存資料庫則用於封存您部署中所有其他使用者的資料。 如果您需要封存資料庫，您可以在監視資料庫、持續聊天資料庫、持續聊天規範資料庫，或頂層端池中的後端伺服器上 collocated 資料庫。 如需規劃適當的存檔拓撲的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的存檔規劃](lync-server-2013-planning-for-archiving.md)。

  - 主管或主管擁有者，如果您想要協助將 Lync Server 2013 使用者要求的復原和重新導向到使用者的主文件，這可以是企業版前端池或標準版伺服器。 我們建議您在支援外部使用者存取的每個中央網站，以及您部署一個或多個前端池的每個中心網站中，部署一個主管或主管池。 每個控制器池最多可以包含10個控制器。 控制器無法與任何其他伺服器角色 collocated。 如需規劃適當控制器拓撲的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的主管案例](lync-server-2013-scenarios-for-the-director.md)。

  - 反向 proxy （不是 Lync Server 2013 元件），但如果您想要支援與同盟使用者共用網頁內容，或支援行動性流量，則需要。 您無法使用任何 Lync Server 2013 伺服器角色來 collocate 反向 proxy 伺服器，但您可以在組織中針對其他人設定支援，以對 Lync Server 2013 部署執行反向 proxy 支援。程式. 如需反向 proxy 伺服器的詳細資料，請參閱部署檔中的[Lync Server 2013 設定反向 proxy 伺服器](lync-server-2013-setting-up-reverse-proxy-servers.md)。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中，A/V 會議、監視及封存都是在前端伺服器上執行，不會再個別伺服器角色。



</div>

您在中央網站上部署的所有前端池和標準版伺服器共用您針對中心網站部署的下列任何一項：

  - 主管或主管池

  - 獨立的中繼伺服器或池

  - Office Web Apps 伺服器

  - Edge 伺服器或 Edge 池

  - 持續聊天伺服器或池

  - 監視

  - 封存

<div>


> [!NOTE]  
> 如果您想要支援 Exchange 2013 整合通訊，但不是 Lync Server 2013 網站的元件，則可以使用 Lync Server 2013 部署來實施 Exchange UM 伺服器。



</div>

多個中心網站也可以共用您在一個中央網站中部署的下列任何一項：

  - 獨立的中繼伺服器或池

  - Edge 伺服器或 Edge 池

  - 持續聊天伺服器或池

  - 封存

  - 監視

<div>


> [!NOTE]  
> Exchange UM 伺服器可以在您的 Lync Server 2013 部署中執行，並由多個中央網站共用，但它不是 Lync Server 2013 網站的元件。



</div>

如需 Lync Server 2013 伺服器角色和功能的詳細資訊，請參閱規劃檔中的[Lync server 2013 中的伺服器角色](lync-server-2013-server-roles.md)。

如需 Lync Server 2013 server collocation 支援摘要，請參閱[Lync server 2013 中的支援的伺服器 collocation](lync-server-2013-supported-server-collocation.md)。

除了本節前面所述的伺服器角色和功能之外，Lync Server 2013 還有其他元件和選項，其中包括下列部分或全部選項：

  - 道

  - PSTN 閘道（如果部署企業版語音）

  - Exchange UM 伺服器

  - DNS 負載平衡

  - 硬體負載平衡器

  - SQL Server 資料庫

  - 檔案共用

如需所有 Lync Server 2013 功能、元件及選項的詳細資料，請參閱規劃檔。

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a>分支網站拓撲與元件（內部部署）

分支網站與中央網站相關聯，且分支網站中的每個 Survivable 分支裝置都與相關聯的中央網站中的企業版前端池或標準版伺服器相關聯。 分支網站在中心網站上的功能大部分，所以分支網站上的元件只包含下列專案：

  - Survivable 分支裝置，將公用的交換電話網絡（PSTN）閘道與一些 Lync Server 功能結合在一起。 您可以在 Survivable 分支裝置上，將中繼伺服器與註冊機構的實例 collocated，而且您可以部署獨立的中繼伺服器或轉送伺服器池。

  - Survivable 分支伺服器，這是執行 Windows Server 且已安裝 Lync Server 2013 註冊機構和中繼伺服器軟體的伺服器。

  - 獨立的 PSTN 閘道（不是 Survivable 分支裝置的一部分）和獨立的中繼伺服器。

Survivable 分支伺服器的需求與任何 Lync Server 2013 伺服器角色的需求相同。

</div>

</div>

<span> </span>

</div>

</div>

</div>

