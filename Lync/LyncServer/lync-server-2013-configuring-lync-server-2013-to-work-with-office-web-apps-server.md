---
title: 將 Lync Server 2013 設定為使用 Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ba6926af243b15449c5b8baa4b29706a2ec8ade
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a>將 Lync Server 2013 設定為使用 Office Web Apps Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-04-22_

在您可以將 Lync Server 2013 設定為使用 Office Web Apps Server 之前，必須先部署並設定 Office Web Apps 伺服器。 如需有關如何安裝及設定單一 Office Web Apps 伺服器的詳細資訊，請參閱檔**指南**，或瞭解如何安裝和設定 Office Web Apps 伺服器群以獲得高可用性的詳細資訊。

成功安裝 Office Web Apps 伺服器並正確設定您的網站伺服器之後，您必須將 Lync Server 設定為與新伺服器通訊;這是透過將 Office Web Apps Server 探索 URL 新增到您的 Lync Server 拓撲中來完成。 若要將 Office Web Apps 伺服器新增到拓撲中，請完成下列步驟：

1.  按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。

2.  在 [**拓撲**建立器] 對話方塊中，選取 [**從現有的部署下載拓撲結構**]，然後按一下 **[確定]**。

3.  在 [**將拓朴儲存為**] 對話方塊中，于 **[檔案名]** 方塊中輸入拓撲檔的名稱（例如， **PreWebAppsServerTopology**），然後按一下 [**儲存**]。 如果您在新的拓撲中遇到問題，可在稍後檢索並重新發佈此拓撲。

4.  在 [拓撲結構建立器] 中，展開 [ **Lync Server 2013**]，展開您的網站名稱，展開 [**企業版前端池**]，以滑鼠右鍵按一下其中一個池的名稱，然後按一下 [**編輯屬性**]。

5.  在 [**編輯屬性**] 對話方塊的 [**一般**] 索引標籤上，找到 [**關聯 Office Web Apps 伺服器**] 的 [標題]，然後按一下下拉式清單中的 [**新增**] （或選取現有的 Office Web Apps 伺服器）。

6.  在 [**定義新的 Office Web Apps 伺服器**] 對話方塊的 [ **Office WEB apps server FQDN** ] 方塊中，輸入您 office web apps server 電腦的完整功能變數名稱（FQDN）;當您這樣做時，您的 Office Web Apps 伺服器探索 URL 應該會自動輸入至 [ **Office Web Apps server 探索 url** ] 方塊中。
    
    如果 Office Web Apps 伺服器安裝于內部部署，且位於與 Lync Server 2013 相同的網路區域中，則不應選取 [ **Office Web Apps 伺服器] 部署在外部網路（也就是 [週邊/網際網路]）** 。
    
    如果 Office Web Apps 伺服器是在您的內部防火牆外部署，請選取 [ **Office Web Apps 伺服器] 部署在外部網路（也就是 [週邊/網際網路]）**。

7.  在 [**定義新的 Office Web Apps Server** ] 對話方塊中，按一下 **[確定]**，然後按一下 [**編輯屬性**] 對話方塊中的 **[確定**]。 然後，Office Web Apps 探索 URL 就會列為其中一個池的關聯。

您必須針對需要與您的 Office Web Apps 伺服器相關聯的每個池重複此程式。

將探索 URL 新增到拓撲之後，您必須發佈此更新的拓撲。 若要在拓撲建立器中執行此動作：

1.  按一下 [**動作**]，然後按一下 [**發佈拓撲**]。

2.  在 [發佈拓撲嚮導] 的 [**發佈拓撲**] 頁面上，按一下 **[下一步]**。

3.  在 [**發佈嚮導完成]** 頁面上，按一下 **[完成]**。

4.  關閉拓撲建立器。

</div>

<span> </span>

</div>

</div>

</div>

