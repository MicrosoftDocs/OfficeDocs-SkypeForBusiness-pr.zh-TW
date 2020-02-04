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
ms.openlocfilehash: b22115bf137c388fd6cd15103ac882056affa4f6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a>Lync Server 2013 中的伺服器角色

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

運行 Lync Server 的每個伺服器都執行一或多個*伺服器角色*。 伺服器角色是該伺服器所提供的一組 Lync 伺服器功能。 您不需要在您的網路中部署所有可用的伺服器角色。 只安裝包含所需功能的伺服器角色。

即使您不熟悉 Lync Server 中的伺服器角色，規劃工具也可以根據您所需的功能，為您提供所需部署之伺服器的最佳解決方案。 本節簡要說明伺服器角色及其提供的一般功能：

  - Standard Edition Server

  - 前端伺服器和後端伺服器

  - Edge 伺服器

  - 中繼伺服器

  - Director

  - 持續聊天前端伺服器

  - 持續聊天存放區（持續聊天后端伺服器）

  - 持續交談合規性存放區（持續式聊天規範後端伺服器）

針對大部分的伺服器角色，如需可伸縮性和高可用性，您可以將多個伺服器的*pool*部署在執行相同的伺服器角色。 池中的每個伺服器都必須執行相同的伺服器角色或角色。 針對 Lync Server 中的大部分類型的 pool，您必須部署負載平衡器，以便在池中的各個伺服器之間散佈流量。 Lync Server 同時支援網域名稱系統（DNS）負載平衡與硬體負載平衡器。

<div>

## <a name="standard-edition-server"></a>Standard Edition Server

標準版伺服器專為小型組織設計，且適用于大型組織的試驗專案。 它能讓 Lync Server 的許多功能（包括必要的資料庫）都能在單一伺服器上執行。 這可讓您以較低的成本進行 Lync Server 功能，但不會提供真正的高可用性方案。

標準版伺服器可讓您使用立即訊息（IM）、目前狀態、會議和企業語音，所有都是在一部伺服器上執行。

針對高可用性方案，請使用 Lync Server 企業版。

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a>前端伺服器和後端伺服器

在 Lync Server 企業版中，前端伺服器是核心伺服器角色，並執行許多基本的 Lync 伺服器功能。 前端伺服器（以及後端伺服器）是在任何 Lync Server 企業版部署中唯一需要的伺服器角色。

[*前端] 池*是一組前端伺服器（配置相同），共同作業為使用者群組提供服務。 多台執行相同角色的伺服器池提供可伸縮性和容錯移轉功能。

前端伺服器包括下列各項：

  - 使用者驗證與註冊

  - 目前狀態資訊與連絡人卡片交換

  - 通訊錄服務與通訊群組清單展開

  - IM 功能，包括多方 IM 會議

  - 網路會議、PSTN 電話撥入式會議及 A/V 會議（如果已部署）

  - 針對 Lync Server 隨附的兩個應用程式（例如，會議助理與回應群組應用程式）和協力廠商應用程式的應用程式託管

  - 您也可以選擇監視，以收集通話詳細資料記錄（CDRs）的使用方式資訊，並呼叫錯誤記錄（Cer）。 此資訊提供有關透過企業語音通話和 A/V 會議來遍歷您網路之媒體質量（音訊與影片）的統計資料。

  - 網頁元件（例如網頁排程程式及加入啟動器）支援的 web 工作。

  - 您可以選擇性地封存 IM 通訊與會議內容，以符合合規性的原因。 如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的存檔規劃](lync-server-2013-planning-for-archiving.md)。
    
    在 Lync Server 2010 和早期版本中，監視及封存是獨立的伺服器角色，而不是在前端伺服器上 collocated。

  - 您也可以選擇是否已啟用持續聊天、聊天室管理的持續聊天 Web 服務和檔案上傳/下載的持續聊天 Web 服務。

前端池也是使用者和會議資料的主要存儲區。 每個使用者的相關資訊會在池中的三個前端伺服器之間複製，並在後端伺服器上備份。

此外，部署中的一個前端池也會執行*中央管理伺服器*，該伺服器會將基本配置資料管理並部署到執行 Lync Server 的所有伺服器。 中央管理伺服器也提供 Lync Server 管理命令介面和檔案傳輸功能。

後端伺服器是執行 Microsoft SQL Server 的資料庫伺服器，可為前端池提供資料庫服務。 後端伺服器可做為池使用者與會議資料的備份儲存，而且是其他資料庫（例如回應群組資料庫）的主要存儲區。 您可以使用單一後端伺服器，但建議使用 SQL Server 鏡像的解決方案，以進行容錯移轉。 後端伺服器不會執行任何 Lync Server 軟體。

<div>


> [!IMPORTANT]  
> 我們不建議將 Lync Server 資料庫與其他資料庫 collocating。 如果您這麼做，可用性和效能可能會受到影響。



</div>

儲存在後端伺服器資料庫中的資訊包含目前狀態資訊、使用者的連絡人清單、會議資料，包括所有目前會議狀態的永久性資料，以及會議排程資料。

</div>

<div>

## <a name="edge-server"></a>Edge 伺服器

Edge 伺服器可讓您的使用者與組織防火牆以外的使用者進行通訊及共同作業。 這些外部使用者可以包含組織自己的使用者，這些使用者目前正在異地作業、同盟夥伴組織的使用者，以及受邀加入 Lync Server 部署之會議的外部使用者。 Edge 伺服器也可連線至公用 IM 聯機服務，包括 Windows Live、AOL、Yahoo\!和 Google 交談。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。 擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟 信使，直到服務關閉日期為止。 AOL 和 Yahoo！的存留期結束日期為2014年6月 已公佈。 如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權 名單. Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</P>
> <LI>
> <P>Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。 與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。 您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</P></LI></UL>



</div>

部署 Edge 伺服器也會啟用行動裝置服務，支援行動裝置上的 Lync 功能。 使用者可以使用支援的 Apple iOS、Android、Windows Phone 或 Nokia 行動裝置來執行諸如傳送和接收立即訊息、查看連絡人及查看目前狀態等活動。 此外，行動裝置支援一些企業語音功能，例如按一下以加入會議、透過工作撥打電話、單一號碼達到、語音信箱及未接來電。 行動裝置功能也支援不支援在背景中執行之應用程式之行動裝置的*推播通知*。 推播通知是傳送給行動裝置的通知，在行動應用程式處於非使用中時，發生該事件。

Edge 伺服器也包含完全整合的可擴展訊息和目前狀態通訊協定（XMPP） proxy，並包含在前端伺服器上的 XMPP 閘道。 您可以設定這些 XMPP 元件，讓您的 Lync Server 2013 使用者從 XMPP 的合作夥伴（例如 Google 交談）新增連絡人，以進行立即訊息和目前狀態。

如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)。

</div>

<div>

## <a name="mediation-server"></a>中繼伺服器

中繼伺服器是用來實現企業語音和電話撥入式會議的必要元件。 轉送伺服器會轉譯信號，在某些設定中，您內部 Lync 伺服器基礎結構與公用交換式電話網絡（PSTN）閘道、IP PBX 或會話初始通訊協定（SIP）幹線之間的媒體。 您可以在與前臺伺服器相同的伺服器上執行轉送服務伺服器 collocated，或將它分割成獨立的中繼伺服器池。

如需詳細資訊，請參閱規劃檔中的[Lync server 2013 中的 [轉送伺服器元件](lync-server-2013-mediation-server-component.md)]。

</div>

<div>

## <a name="director"></a>Director

控制器可驗證 Lync Server 使用者要求，但不會提供使用者帳戶或提供目前狀態或會議服務。 在能讓外部使用者存取的部署中加強安全性時，控制器是最實用的。 Director 可以在將要求傳送到內部伺服器前進行驗證。 在拒絕服務攻擊的情況下，攻擊會以控制器為結束，而且不會到達前端伺服器。 如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的主管案例](lync-server-2013-scenarios-for-the-director.md)。

</div>

<div>

## <a name="persistent-chat-server-roles"></a>持續聊天伺服器角色

持續聊天可讓使用者參與多方、在一段時間內保持的、以主題為基礎的交談。 持續聊天前端伺服器會執行持續聊天服務。 持續式聊天后端伺服器會儲存聊天記錄資料，以及類別和聊天室的相關資訊。 選用的持續性聊天規範後端伺服器可以儲存聊天內容和相容性事件，以符合合規性的目的。

運行 Lync Server 標準版的伺服器也可以在同一個伺服器上執行持續聊天 collocated。 您無法 collocate 與企業版前端伺服器的永久聊天前端伺服器。

如需詳細資訊，請參閱[在 Lync server 2013 中規劃持久聊天伺服器](lync-server-2013-planning-for-persistent-chat-server.md)。

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的中繼伺服器元件](lync-server-2013-mediation-server-component.md)  


[在 Lync Server 2013 中規劃封存](lync-server-2013-planning-for-archiving.md)  
[在 Lync Server 2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)  
[Lync Server 2013 中的 Director 案例](lync-server-2013-scenarios-for-the-director.md)  
[在 Lync Server 2013 中規劃常設聊天室伺服器](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

