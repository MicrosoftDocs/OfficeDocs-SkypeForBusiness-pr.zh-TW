---
title: Lync Server 2013：檢查磁片使用量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking disk usage
ms:assetid: 0f0cb9bf-3f11-43ff-be10-5c8e1b5c4f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720908(v=OCS.15)
ms:contentKeyID: 63969578
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 554b493ba7ca837a8ea5c80f6751ddb91061c374
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-disk-usage-in-lync-server-2013"></a>在 Lync Server 2013 中檢查磁片使用量

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-04-30_

硬碟磁片磁碟機是 Lync Server 2013 部署的一個重要元件。 若沒有足夠的可用磁碟空間，作業系統和 Lync Server 2013 資料庫都無法正常運作。 您必須每天監視 Lync Server 2013 後端資料庫統計資料，以協助確保伺服器不會用盡磁碟空間，並準備根據需要新增儲存資源。

除了檢查託管作業系統、程式檔案、資料庫及交易處理記錄（Lync Server 2013 後端）的磁碟空間，您也應該監視檔案系統的使用方式，這些檔案系統包含下列重要檔案共用的磁碟空間資料

  - 會議內容

  - 會議內容中繼資料

  - 會議合規性記錄

  - 應用程式資料檔案（由應用程式伺服器元件在內部使用）

  - 群組聊天伺服器 web 服務與合規性資料夾（儲存已上傳到群組聊天網頁服務的檔案）

  - 群組聊天合規性 XML 檔案（包含群組聊天合規性記錄）

  - 更新檔案（適用于裝置更新服務）

  - 通訊錄檔案

Lync Server 2013 需要硬碟空間來儲存其資料庫及事務記錄記錄，以及先前所列的檔案共用中的檔案。

您應該定期監視磁碟空間，以協助確保 Lync Server 2013 部署由於儲存資源不足而不會受到負面影響。

針對每個 Lync Server 2013 容量與預期的資料庫及事務記錄檔增長，比較並維持有關可用磁碟空間的統計資訊。 這有助於在儲存資源需要時，進行容量規劃並新增儲存空間。

為了適應疑難排解及災害復原的情況，建議可用的可用磁碟空間大小等於或大於資料庫大小的110%。

您可以使用下列方法來查看可用磁碟空間：

1.  **系統中心作業管理員**   系統中心作業管理員可以用來在卷空間受到限制時向管理員發出警告。

2.  ****    如果可用的硬碟空間低於20%，您可以執行腳本來傳送一則腳本來監視磁碟空間，以傳送訊息給您。 您可以在 TechNet 上的 Microsoft 腳本中心找到範例腳本，請檢查：[http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)

3.  **Windows 資源管理器**   使用 windows 資源管理器來檢查儲存 Lync Server 2013 記錄和資料庫之磁片卷的磁碟空間。

</div>

<span> </span>

</div>

</div>

</div>

