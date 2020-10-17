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
ms.openlocfilehash: 6379d110fc25ba31062d211d3893567ad92fda1f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526200"
---
# <a name="checking-disk-usage-in-lync-server-2013"></a>在 Lync Server 2013 中檢查磁片使用量

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-04-30_

硬碟磁片磁碟機是 Lync Server 2013 部署的重要元件。 若沒有足夠的可用磁碟空間，作業系統和 Lync Server 2013 資料庫皆無法正常運作。 您必須每天監視 Lync Server 2013 後端資料庫統計資料，以確保伺服器不會耗盡磁碟空間，並準備好視需要新增儲存體資源。

除了檢查主控作業系統、程式檔、資料庫和交易記錄的磁碟空間之外 (Lync Server 2013 後端) 之外，您還應該監視包含下列重要資料的檔案共用磁碟空間的檔案系統使用狀況：

  - 會議內容

  - 會議內容中繼資料

  - 會議規範記錄

  - 應用程式伺服器元件 (內部使用的應用程式資料檔案) 

  - Group Chat Server web service 和合規性資料夾 (儲存上傳至群組聊天 web 服務的檔案) 

  - 包含群組聊天規範記錄的群組聊天規範 XML 檔案 () 

  - 更新裝置更新服務的 (檔案) 

  - 通訊錄檔案

Lync Server 2013 除先前所列檔案共用上的檔案之外，還需要硬碟空間來儲存其資料庫和交易記錄。

您應該定期監控磁碟空間，以協助確保 Lync Server 2013 部署不會因為儲存資源不足而受到不良影響。

比較及維護每個 Lync Server 2013 磁片區上可用磁碟空間的統計資訊，以及資料庫及交易記錄檔的預期成長。 這可協助您進行容量規劃，並在需要儲存資源時新增儲存體。

為了容納疑難排解與嚴重損壞修復的情況，建議可用的磁片區空間大小等於或大於資料庫大小的110%。

您可以使用下列方法來檢查可用的磁碟空間：

1.  **System Center Operations Manager**    在限制磁片區空間時，可以使用 System Center Operations Manager 來警告管理員。

2.  執行**腳本**    執行腳本以監視磁碟空間（如果可用的硬碟空間低於20%）。 您可以在 TechNet 上的 [Microsoft Script Center] 中找到範例腳本，請檢查： [https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)

3.  **Windows Explorer**    使用 Windows Explorer 檢查儲存 Lync Server 2013 記錄和資料庫之磁片區上的磁碟空間。

</div>

<span> </span>

</div>

</div>

</div>

