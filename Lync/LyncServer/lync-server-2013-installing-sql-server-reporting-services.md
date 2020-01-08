---
title: Lync Server 2013：安裝 SQL Server Reporting Services
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6707cafc3a08123bd2189639704741681eb9cdd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a>在 Lync Server 2013 中安裝 SQL Server Reporting Services

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-20_

如果您想要使用 Microsoft Lync Server 2013 監視報告（如需詳細資訊，請參閱本檔的下一節），您必須先安裝 SQL Server Reporting Services;您可以在安裝 Microsoft SQL Server 或安裝 SQL Server 之後的任何時間安裝 Reporting Services。 如果您尚未安裝 SQL Server，請依照本檔前面所提供的指示進行。 安裝 SQL Server 時，請確定在 [功能選擇] 頁面上選取 [Reporting Services]。 這會安裝 SQL Server Reporting Services。

如果您已安裝 SQL Server，但未安裝 SQL Server Reporting Services，您可以根據適當的方式，按照適當的 SQL Server 2008 R2 或 SQL Server 2012 一組適當的指示來新增該功能。

若要確認已成功安裝報表服務，請完成下列步驟：

1.  如果您執行的是 Microsoft SQL Server 2008 R2，請按一下 [**開始**]，按一下 [**所有程式**]，按一下 **[Microsoft SQL Server 2008 R2**]，按一下 [設定**工具**]，然後按一下 [ **Reporting Services Configuration Manager**]。
    
    如果您執行的是 Microsoft SQL Server 2012，請按一下 [**開始**]，按一下 [**所有程式**]，按一下 **[Microsoft SQL Server 2012**]，按一下 [設定**工具**]，然後按一下 [ **Reporting Services Configuration Manager**]。

2.  在 [ **Reporting Services**設定連線] 對話方塊中，確認您的伺服器名稱出現在 [**伺服器名稱**] 方塊中，而且儲存監視資料的 SQL server 實例名稱會出現在 [**報表伺服器實例**] 方塊中。 按一下 **[連線]**。

在 Reporting services 組態管理員中，報表伺服器狀態窗格會顯示已安裝 SQL Server Reporting Services，且目前正在執行報表服務：報表伺服器狀態應該顯示為 [**已啟動**]，且 [**開始**] 按鈕應該呈現灰色且無法使用。 如果報表服務未在執行，請按一下 [**開始**] 以啟動服務。

如果報表伺服器資料庫名稱標籤旁沒有列出任何資料庫，請執行下列動作：

1.  在 Reporting Services 組態管理員中按一下 [**資料庫**]。

2.  在 [報表伺服器資料庫] 窗格中，按一下 [**變更資料庫**]。

3.  在報表伺服器資料庫設定精靈的 [動作] 窗格中，選取 [**建立新報表伺服器資料庫**]，然後按一下 **[下一步]**。

4.  在報表伺服器資料庫設定精靈的 [資料庫伺服器] 窗格中，確認 [**伺服器名稱**]、[**驗證類型**] 和 [使用者名稱 **] 方塊中**所列的資訊正確無誤。 按一下 [**測試**連線]，確認您可以連線到資料庫伺服器，然後按 **[下一步]**。

5.  在報表伺服器資料庫設定向導的 [資料庫] 窗格中，接受 [**資料庫名稱**]、[**語言**] 和 [**報表伺服器模式**] 的預設值，然後按 **[下一步]**。

6.  在報表伺服器資料庫設定向導的 [認證] 窗格中，確認 [**驗證類型**] 下拉式清單和 [**使用者名稱**] 和 [**密碼**] 方塊中列出的資訊正確無誤，然後按一下 **[下一步]**。

7.  在報表伺服器資料庫設定精靈中，按一下 [摘要窗格] 中的 **[下一步**]。

8.  在報表伺服器資料庫設定精靈中，按一下 [進度] 和 [完成] 窗格中的 **[完成**]。

若要確認已設定 Reporting Services Url，請按一下 [ **Web 服務 url**]。 您應該會在 [標題**報表伺服器] Web 服務 url**底下看到一個或多個 url。 按一下每個 Url，確認您可以在 [首頁] 頁面上找到 SQL Server Reporting Services 的本機安裝。

</div>

<span> </span>

</div>

</div>

</div>

