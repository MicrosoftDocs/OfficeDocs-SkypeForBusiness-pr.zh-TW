---
title: Lync Server 2013：部署企業語音
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae445d954bd1be7c956d76aa48da2ad7854c6a54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a>在 Lync Server 2013 中部署企業版語音

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

Lync Server 2013，企業語音是 Lync Server 2013 基礎結構的一部分。

部署企業語音要求您：

<div id="sectionSection0" class="section">

1.  請在規劃檔的 [ [Lync Server 2013] 區段中，查看企業語音規劃](lync-server-2013-planning-for-enterprise-voice.md)。

2.  使用此工作負載來完成要部署之功能和元件的方案。

3.  執行規劃工具以設計反映您部署決定的拓撲。

4.  如在 [部署檔] 中的 [ [Lync Server 2013] 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)，請在 [拓撲建立器] 中開啟拓撲設計。
    
    <div>
    

    > [!NOTE]  
    > [拓撲建立器] 的安裝是內部池之部署程式的一部分。 如需詳細資訊，請參閱在部署檔中<A href="lync-server-2013-install-lync-server-administrative-tools.md">安裝 Lync Server 2013 系統管理工具</A>。

    
    </div>

此外，您還必須已在中央網站和分支網站上部署 Lync Server、企業版，且對應到您選擇要部署的參考拓撲。 您必須先定義、發佈及安裝至少一個內部池的檔案，才能部署企業語音元件，而且您必須使用拓撲建立器來定義及發佈內部池。

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

若要查看含企業語音伺服器角色（以及它們與其他 Lync Server 2013 伺服器角色）的範例，請參閱規劃檔中的[Lync server 2013 中的參考拓撲](lync-server-2013-reference-topologies.md)。

若要查看說明並說明範例呼叫許可控制部署（包括網路區域、網路網站和子網）的參照拓朴，請參閱在規劃檔中的[Lync Server 2013 中收集您對通話許可控制的需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> 若要在中央網站部署企業語音，請繼續閱讀本節中的主題。 若要在分支網站上部署企業語音，請跳過部署檔中的<A href="lync-server-2013-deploying-branch-sites.md">Lync Server 2013 中的 [部署分支網站</A>]。



</div>

本節包含適用于部署的程式，其中，在每個前端伺服器或標準版伺服器上 collocated 的中繼伺服器（如有建議），以及使用獨立的中繼伺服器池的部署。

如果您使用拓撲建立器定義併發布在每個前端伺服器或標準版伺服器上 collocates 轉送伺服器的拓撲，就可以略過下列內容，因為部署嚮導已自動安裝檔案供當您為前端伺服器池或標準版伺服器安裝檔案時，會進行中繼伺服器：

  - [在 Lync Server 2013 中設定主幹](lync-server-2013-configuring-trunks.md)

如果您使用拓撲建立器在獨立的池中定義併發布轉送伺服器，您可以使用下列內容：

  - 請確認您的拓撲符合軟體與環境的先決條件，如[Lync Server 2013 的企業語音先決條件](lync-server-2013-enterprise-voice-prerequisites.md)中所述。

</div>

<div>

## <a name="in-this-section"></a>本節內容

  - <span></span>  
    [Lync Server 2013 的企業語音先決條件](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [在 Lync Server 2013 中部署中繼伺服器並定義對等項目](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [在 Lync Server 2013 中設定主幹](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [在 Lync Server 2013 中設定撥號對應表](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [在 Lync Server 2013 中設定語音原則、PSTN 使用方式記錄及語音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [在 Lync Server 2013 中匯出和匯入語音路由組態](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [在 Lync Server 2013 中測試語音路由](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [在 Lync Server 2013 中發佈語音路由設定的擱置變更](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [部署內部部署的 Exchange UM，以提供 Lync Server 2013 語音信箱](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [在主控 Exchange UM 上提供 Lync Server 2013 使用者語音信箱](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [配置與 Exchange Online 的內部部署 Lync Server 2013 整合](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [在 Lync Server 2013 中部署高級企業語音功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [關於 Lync Server 2013 中的網路區域、網站和子網路](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [在 Lync Server 2013 中建立或修改網路區域](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [在 Lync Server 2013 中建立或修改網站](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [在 Lync Server 2013 中建立子網路與網路站台的關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [在 Lync Server 2013 中設定通話許可控制](lync-server-2013-configure-call-admission-control.md)
    
      - [在 Lync Server 2013 中設定增強型 9-1-1](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [在 Lync Server 2013 中設定媒體旁路](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [在 Lync Server 2013 中啟用企業語音的使用者](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中部署分支網站](lync-server-2013-deploying-branch-sites.md)  
[在 Lync Server 2013 中設定撥入會議](lync-server-2013-configuring-dial-in-conferencing.md)  
[在 Lync Server 2013 中設定通話駐留](lync-server-2013-configuring-call-park.md)  
[在 Lync Server 2013 中設定未指派號碼的宣告](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[在 Lync Server 2013 中部署監視](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

