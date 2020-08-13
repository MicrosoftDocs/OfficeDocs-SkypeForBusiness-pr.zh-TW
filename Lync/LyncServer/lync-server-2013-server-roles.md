---
title: Lync Server 2013 伺服器角色
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e153e41e0c5d452ec136daf2ad46d4ea67541d83
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a>Lync Server 2013 中的伺服器角色

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

每一部執行 Lync Server 的伺服器都會執行一或多個*伺服器角色*。 伺服器角色是該伺服器所提供之 Lync Server 功能的定義集合。 您不需要在您的網路中部署所有可用的伺服器角色。 只安裝包含您想要之功能的伺服器角色。

即使您不熟悉 Lync Server 中的伺服器角色，規劃工具也可以根據您所需的功能，針對您需要部署的伺服器，引導您使用最佳解決方案。 本節提供伺服器角色及其提供的一般功能的簡短概述：

  - Standard Edition Server

  - 前端伺服器及後端伺服器

  - Edge Server

  - 中繼伺服器

  - Director

  - Persistent Chat 前端伺服器

  - Persistent chat Store (Persistent Chat 後端伺服器) 

  - Persistent Chat 合規性存放區 (持續性聊天規範後端伺服器) 

針對大部分的伺服器角色，針對可擴充性和高可用性，您*可以部署多*部伺服器的集區，所有執行相同的伺服器角色。 集區中的每部伺服器都必須執行一或多個相同的伺服器角色。 在 Lync Server 中大多數的集區類型，您必須部署負載平衡器，以在集區中的不同伺服器間散佈流量。 Lync Server 同時支援網域名稱系統 (DNS) 負載平衡與硬體負載平衡器。

<div>

## <a name="standard-edition-server"></a>Standard Edition Server

Standard Edition server 是針對小型組織設計，也適用于大型組織的試驗專案。 它可讓 Lync Server 的許多功能（包括必要的資料庫）在單一伺服器上執行。 這可讓您以較低的成本進行 Lync Server 功能，但不會提供真正的高可用性解決方案。

Standard Edition server 可讓您使用立即訊息 (IM) 、目前狀態、會議及 Enterprise Voice，都是在一部伺服器上執行。

如需高可用性解決方案，請使用 Lync Server Enterprise Edition。

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a>前端伺服器及後端伺服器

在 Lync Server Enterprise Edition 中，前端伺服器是核心伺服器角色，而且會執行許多基本的 Lync Server 功能。 在任何 Lync Server Enterprise Edition 部署中，前端伺服器及後端伺服器都是唯一需要的伺服器角色。

*前端集*區是一組前端伺服器（已正確設定），可共同運作，以提供通用使用者群組的服務。 執行相同角色的多部伺服器集區提供可擴充性和容錯移轉功能。

前端伺服器包含下列專案：

  - 使用者驗證和註冊

  - 目前狀態資訊和連絡人卡片交換

  - 通訊錄服務和通訊群組清單擴充

  - IM 功能（包括多方 IM 會議）

  - 網路會議、PSTN 電話撥入式會議和 A/V 會議 (（若已部署）) 

  - 應用程式裝載，針對 Lync Server 所包含的兩個應用程式 (例如會議助理和回應群組應用程式) ，以及協力廠商應用程式

  - （選用）監控，以 [通話詳細資料記錄] 的形式收集使用資訊 (Cdr) 並呼叫錯誤記錄 (Cer) 。 此資訊提供有關媒體質量 (音訊和影片) 針對企業語音通話和 A/V 會議進行網路的統計資料。

  - 網頁元件至支援的 web 工作，例如 web 排程器及加入啟動器。

  - （選用）封存 IM 通訊和會議內容，以符合合規性的原因。 如需詳細資訊，請參閱規劃檔中的[規劃 Lync Server 2013 中的](lync-server-2013-planning-for-archiving.md)封存。
    
    在 Lync Server 2010 和舊版中，監控和封存是不同的伺服器角色，不會組合在前端伺服器上。

  - （選用）啟用持續性聊天時，會持續聊天網頁服務用於聊天室管理，並可進行檔案上傳/下載的持續性聊天 Web 服務。

前端集區也是使用者和會議資料的主要儲存區。 每個使用者的資訊都會在集區中的三部前端伺服器之間進行複製，並在後端伺服器上備份。

此外，部署中的一個前端集區也會執行*中央管理伺服器*，此伺服器會管理及部署所有執行 Lync Server 的伺服器的基本設定資料。 中央管理伺服器也提供 Lync Server 管理命令介面和檔案傳輸功能。

後端伺服器是執行 Microsoft SQL Server 的資料庫伺服器，提供前端集區的資料庫服務。 後端伺服器充當集區使用者和會議資料的備份存放區，也是其他資料庫（如回應群組資料庫）的主要儲存區。 您可以擁有單一後端伺服器，但建議使用 SQL Server 鏡像的解決方案進行容錯移轉。 後端伺服器不會執行任何 Lync Server 軟體。

<div>


> [!IMPORTANT]  
> 我們不建議使用其他資料庫組合 Lync Server 資料庫。 如果您這麼做，可用性和效能可能會受到影響。



</div>

儲存在後端伺服器資料庫中的資訊包括目前狀態資訊、使用者的連絡人清單、會議資料（包括所有目前會議狀態的持續性資料）和會議排程資料。

</div>

<div>

## <a name="edge-server"></a>Edge Server

Edge Server 可讓您的使用者與組織防火牆外的使用者進行通訊及共同作業。 這些外部使用者可以包含組織的使用者，這些使用者目前在異地工作、同盟夥伴組織的使用者，以及已被邀請加入 Lync Server 部署之會議的外部使用者。 Edge Server 也可連線到公用 IM 聯機服務，包括 Windows Live、AOL、Yahoo \! 和 Google 交談。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 ( 「PIC USL」 ) 不再提供購買新的或更新的協定。 具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟 信使直到服務關閉日期。 AOL 和 Yahoo！的循環結束日期為2014年6月 已宣告。 如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權 信使。 Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</P>
> <LI>
> <P>Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。 與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。 隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</P></LI></UL>



</div>

部署 Edge Server 也會啟用行動裝置，其支援行動裝置上的 Lync 功能。 使用者可以使用支援的 Apple iOS、Android、Windows Phone 或 Nokia 行動裝置執行活動，例如傳送和接收立即訊息、查看連絡人及查看顯示狀態。 此外，行動裝置還可支援某些 Enterprise Voice 功能，例如按一下加入會議、從公司撥號、單一號碼搜尋、語音信箱及未接來電。 行動功能也可以為不支援在背景執行應用程式的行動裝置，支援「推播通知」**。 推播通知是針對在行動應用程式為非使用中狀態時所發生的事件，傳送給行動裝置的通知。

Edge Server 也包含完整整合的可延伸訊息和顯示狀態通訊協定 (XMPP) proxy，包含在前端伺服器上的 XMPP 閘道。 您可以設定這些 XMPP 元件，讓您的 Lync Server 2013 使用者新增來自以 XMPP 為基礎的合作夥伴的連絡人 (例如 Google 交談) 以進行立即訊息與顯示狀態。

如需詳細資訊，請參閱規劃檔中的[規劃 Lync Server 2013 中的外部使用者存取](lync-server-2013-planning-for-external-user-access.md)。

</div>

<div>

## <a name="mediation-server"></a>中繼伺服器

轉送伺服器是用來執行企業語音和電話撥入式會議的必要元件。 轉送伺服器轉譯信號，在某些設定中，您內部 Lync 伺服器基礎結構和公用交換電話網路之間的媒體會 (PSTN) 閘道、IP-PBX 或會話初始通訊協定 (SIP) 主幹。 您可以在前端伺服器所在的伺服器上執行轉送伺服器組合，或將其分割成獨立的轉送伺服器集區。

如需詳細資訊，請參閱規劃檔中的[Lync server 2013](lync-server-2013-mediation-server-component.md)中的轉送伺服器元件。

</div>

<div>

## <a name="director"></a>Director

Director 可驗證 Lync Server 使用者要求，但不會家用使用者帳戶，也不會提供目前狀態或會議服務。 Director 在啟用外部使用者存取的部署中增強安全性是非常有用的。 Director 可以在將要求傳送至內部伺服器之前先驗證要求。 在拒絕服務攻擊的情況下，攻擊會以 Director 結尾，而且不會到達前端伺服器。 如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的 Director 案例](lync-server-2013-scenarios-for-the-director.md)。

</div>

<div>

## <a name="persistent-chat-server-roles"></a>Persistent Chat Server Role

Persistent chat 可讓使用者加入一段時間內的多方、主題型交談。 Persistent Chat 前端伺服器會執行 persistent chat service。 Persistent Chat 後端伺服器會儲存聊天記錄資料，以及類別和聊天室的相關資訊。 選用的持續性聊天規範後端伺服器可以儲存聊天內容和符合性事件，以符合規範的目的。

執行 Lync Server Standard Edition 的伺服器也可以在同一部伺服器上執行 Persistent chat 組合。 您無法以 Enterprise Edition 前端伺服器組合持久聊天前端伺服器。

如需詳細資訊，請參閱[在 Lync server 2013 中規劃 Persistent Chat Server](lync-server-2013-planning-for-persistent-chat-server.md)。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的轉送伺服器元件](lync-server-2013-mediation-server-component.md)  


[在 Lync Server 2013 中規劃封存](lync-server-2013-planning-for-archiving.md)  
[在 Lync Server 2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)  
[Lync Server 2013 中的 Director 案例](lync-server-2013-scenarios-for-the-director.md)  
[在 Lync Server 2013 中規劃 Persistent Chat Server](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

