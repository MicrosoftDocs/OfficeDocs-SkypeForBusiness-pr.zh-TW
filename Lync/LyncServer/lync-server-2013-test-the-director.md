---
title: Lync Server 2013：測試 Director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b82b8b7e494a66cf38fd27e37f322c79e95f801c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a>在 Lync Server 2013 中測試 Director

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

在此階段，您已設定控制器或控制器池，但您的網域名稱系統（DNS） SRV 專案仍指向用戶端，以使用 pool 或標準版伺服器登入。 在變更 DNS 記錄以讓 Lync 2013 用戶端透過使用 Director 自動登入之前，請先透過手動將用戶端指向控制器來測試用戶端。

<div>

## <a name="to-test-the-deployment"></a>測試部署

1.  使用**CSAdministrator**群組中的網域帳戶登入您已安裝 Lync Server [控制台] 的電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在 [功能窗格] 中，按一下 [**拓撲**]，然後在 [Status] （**狀態**）欄中，確認有一個綠色伺服器，其中有箭號（也就是 [![綠色箭頭](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "帶有綠色箭頭的伺服器圖示")]），適用于您的主管或主管池。

4.  將已安裝 Lync Server 2013 用戶端的兩個用戶端電腦連線，然後以不同的使用者帳戶（在每個電腦上啟用 Lync Server 2013）登入。

5.  在其中一個用戶端電腦上，按一下 [**選項**] 功能表，選取 [**個人**設定] 群組，按一下 [**高級**]，按一下 [**手動**設定]，然後將**內部伺服器名稱或 IP 位址**設定為新主管或主管池的完整功能變數名稱（FQDN）。

6.  登入兩個用戶端，並確認使用主管來登入的用戶端能夠順利登入，查看其他使用者的目前狀態，以及他們是否可以交換立即訊息。

</div>

</div>

<span> </span>

</div>

</div>

</div>

