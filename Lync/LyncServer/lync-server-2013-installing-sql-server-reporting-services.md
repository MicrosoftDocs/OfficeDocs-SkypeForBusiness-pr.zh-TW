---
title: Lync Server 2013： 安裝 SQL Server Reporting Services
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e1663bad8515082603a411a42de5c98d7f70594
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a>Lync Server 2013 中安裝 SQL Server Reporting Services

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-06-20 個_

如果您想要使用 Microsoft Lync Server 2013 監視報告 （請參閱此文件的詳細資訊的下一節） 您必須先安裝 SQL Server Reporting Services;Reporting Services 可以安裝在您安裝 Microsoft SQL Server 的同一時間或之後安裝 SQL 伺服器的任何時間。 如果尚未安裝 SQL Server，請遵循本文件中先前提供的指示。 安裝 SQL Server 時，請務必在 [特徵選取] 頁面選取 [Reporting Services]。 如此會安裝 SQL Server Reporting Services。

若已安裝 SQL Server 但未安裝 SQL Server Reporting Services，您可以視情況遵循針對 SQL Server 2008 R2 或 SQL Server 2012 的一組適當指示，新增該特徵。

若要驗證已成功安裝 Reporting Services，請完成下列步驟：

1.  如果執行 Microsoft SQL Server 2008 R2，請依序按一下 **[開始]**、**[所有程式]**、**[Microsoft SQL Server 2008 R2]**、[**組態工具]** 及 **[Reporting Services 組態管理員]**。
    
    如果執行 Microsoft SQL Server 2012，請依序按一下 **[開始]**、**[所有程式]**、**[Microsoft SQL Server 2012]**、**[組態工具]** 及 **[Reporting Services 組態管理員]**。

2.  在 **[Reporting Services 組態連接]** 對話方塊中，確認您伺服器的名稱顯示在 **[伺服器名稱]** 方塊中，而儲存您監控資料之 SQL Server 執行個體的名稱顯示在 **[報表伺服器執行個體]** 方塊中，然後按一下 **[連接]**。

Reporting Service 設定管理員] 中，[報表伺服器狀態窗格應會顯示已安裝 SQL Server Reporting Services 與 Reporting Services 目前正在執行： 將報表伺服器狀態應顯示為 [**已啟動**並**開始**] 按鈕應該灰色，而且無法使用。 如果 Reporting Service 未執行，請按一下 **[啟動]** 以啟動服務。

如果 [報表伺服器資料庫名稱] 標籤旁未列出資料庫，請執行下列作業：

1.  在 Reporting Services 組態管理員中，按一下 **[資料庫]**。

2.  在 [報表伺服器資料庫] 窗格中，按一下 **[變更資料庫]**。

3.  在報表伺服器資料庫組態精靈的 [動作] 窗格中，選取 **[建立新的報表伺服器資料庫]**，然後按 **[下一步]**。

4.  在報表伺服器資料庫組態精靈的 [資料庫伺服器] 窗格中，確認列於 **[伺服器名稱]**、**[驗證類型]** 及 **[使用者名稱]** 方塊中的資訊是否正確。按一下 **[測試連接]** 以驗證可以連接至資料庫伺服器，然後按 **[下一步]**。

5.  在報表伺服器資料庫組態精靈的 [資料庫] 窗格中，接受 **[資料庫名稱]**、**[語言]** 及 **[報表伺服器模式]** 的預設值，然後按 **[下一步]**。

6.  在報表伺服器資料庫組態精靈的 [認證] 窗格中，確認列於 **[驗證類型]** 下拉式清單、**[使用者名稱]** 及 **[密碼]** 方塊中的資訊是否正確，然後按 **[下一步]**。

7.  在報表伺服器資料庫組態精靈的 [摘要] 窗格中，按 **[下一步]**。

8.  在報表伺服器資料庫組態精靈的 [進度和完成] 窗格中，按一下 **[完成]**。

若要驗證是否設定 Reporting Service URL，請按一下 **[Web 服務 URL]**。應該見到在 **[報表伺服器 Web 服務 URL]** 標題下列出一個或多個 URL。請逐一按一下這些 URL，確認是否可以存取本機安裝 SQL Server Reporting Services 的首頁。

</div>

<span> </span>

</div>

</div>

</div>

