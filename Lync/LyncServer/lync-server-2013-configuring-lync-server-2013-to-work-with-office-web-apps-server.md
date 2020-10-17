---
title: 設定 Lync Server 2013 以使用 Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd362d42dd3d2927b15ff567343c116209a67e7e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517356"
---
# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a>設定 Lync Server 2013 以使用 Office Web Apps Server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-04-22_

在您將 Lync Server 2013 設定為使用 Office Web Apps Server 之前，必須先部署及設定 Office Web Apps Server。 如需如何安裝及設定單一 Office Web Apps Server，或如何安裝及設定 Office Web Apps Server 陣列以取得高可用性的詳細資訊，請參閱**部署 Office Web Apps Server 與 Office Web Apps 指南**文件。

成功安裝 Office Web Apps Server 並正確設定網頁伺服器陣列後，您必須將 Lync Server 設定為與新伺服器通訊;若要將 Office Web Apps Server 探索 URL 新增至 Lync Server 拓撲，可執行此動作。 若要將 Office Web Apps Server 新增至拓撲，請完成下列步驟：

1.  依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。

2.  在 **[拓撲產生器]** 對話方塊中，選取 **[從現有的部署下載拓撲]**，然後按一下 **[確定]**。

3.  在 **[另存拓撲]** 對話方塊的 **[檔案名稱]** 方塊中，鍵入拓撲文件的名稱 (例如 **PreWebAppsServerTopology**)，然後按一下 **[儲存]**。如果新拓撲之後發生問題，就可以擷取並重新發行此拓撲。

4.  在 [拓撲產生器] 中，依序展開 [ **Lync Server 2013**] 和您的網站名稱，展開 [ **Enterprise Edition 前端**集區]，以滑鼠右鍵按一下其中一個集區的名稱，然後按一下 [ **編輯屬性**]。

5.  在 **[編輯內容]** 對話方塊的 **[一般]** 索引標籤上，尋找標題 **[關聯 Office Web Apps Server]**，然後按一下 **[新增]** (或從下拉式清單中選取現有的 Office Web Apps Server)。

6.  在 **[定義新的 Office Web Apps Server]** 對話方塊的 **[Office Web Apps Server FQDN]** 方塊中，鍵入 Office Web Apps Server 電腦的完整網域名稱 (FQDN)；執行此動作時，您的 Office Web Apps Server 探索 URL 應自動輸入至 **[Office Web Apps Server 探索 URL]** 方塊。
    
    如果 Office Web Apps Server 安裝于內部部署，且與 Lync Server 2013 位於相同的網路區域中，則選項 **Office Web Apps server 部署在外部網路中 (也就是說，不應該選取周邊/網際網路) ** 。
    
    如果 Office Web Apps Server 部署在內部防火牆外，則選取 **[Office Web Apps Server 部署在外部網路 (亦即周邊/網際網路]** 選項。

7.  在 **[定義新的 Office Web Apps Server]** 對話方塊中，按一下 **[確定]**，然後按一下 **[編輯內容]** 對話方塊中的 **[確定]**。Office Web Apps 探索 URL 將會列為其中一個集區的關聯。

您必須對每個需要與 Office Web Apps Server 建立關聯的集區重複此程序。

在新增探索 URL 至拓撲後，必須發行此更新的拓撲。在拓撲產生器中執行此作業的步驟如下：

1.  按一下 **[動作]**，然後按一下 **[發行拓撲]**。

2.  在發行拓撲精靈的 **[發行拓撲]** 頁面上，按 **[下一步]**。

3.  在 **[發行精靈完成]** 頁面上，按一下 **[完成]**。

4.  關閉拓撲產生器。

</div>

<span> </span>

</div>

</div>

</div>

