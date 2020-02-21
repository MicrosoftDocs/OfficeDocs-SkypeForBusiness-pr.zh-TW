---
title: Lync Server 2013： 檢查磁碟使用狀況
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
ms.openlocfilehash: d0cb167d2a7aed3f5c107d4beba568c00ac501e0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="checking-disk-usage-in-lync-server-2013"></a>Lync Server 2013 中的檢查磁碟使用狀況

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-04-30_

硬碟機是 Lync Server 2013 部署的重要元件。 沒有足夠的可用磁碟區，作業系統和 Lync Server 2013 資料庫都可以正常運作。 您必須監視的 Lync Server 2013 後端資料庫統計資料每日可協助確定伺服器不要執行磁碟空間不足，並準備視需要新增存放裝置資源。

不同於檢查上主控的作業系統，程式檔案、 資料庫和交易記錄檔 （Lync Server 2013 後端） 的磁碟空間，您也應該監視包含磁碟空間可供包含下列重要的檔案共用的檔案系統的使用方式資料：

  - 會議內容

  - 會議內容中繼資料

  - 會議規範記錄

  - 應用程式資料檔案 （用於內部應用程式伺服器元件）

  - 群組聊天伺服器 web 服務及符合性資料夾 （若要儲存檔案上傳到 [Group Chat web 服務）

  - 群組聊天規範的 XML 檔案 （包含 Group Chat 規範記錄）

  - 更新檔案 （適用於裝置更新服務）

  - 通訊錄檔案

Lync Server 2013 所需的硬碟空間來儲存其資料庫與交易記錄檔，除了先前所列的檔案共用上的檔案。

您應監視的磁碟空間，定期可協助確定 Lync Server 2013 部署不產生負面影響因為沒有足夠的儲存資源。

比較和維護每個 Lync Server 2013 的磁碟區與資料庫和交易記錄檔的預期的成長上可用的磁碟空間的統計資訊。 這可協助容量規劃及必要的存放裝置資源時新增存放裝置。

若要容納疑難排解和嚴重損壞修復情況下，我們建議您提供的可用磁碟區空間為等於或大於資料庫大小的 110%。

您可以使用下列方法來檢查可用磁碟空間：

1.  **System Center Operations Manager**   System Center Operations Manager 可用來警告系統管理員，當磁碟區空間會受到限制。

2.  **執行指令碼**   執行傳送郵件給您，如果的可用硬碟空間低於 20%的指令碼，以監視磁碟空間。 您可以找到 Microsoft TechNet 上的指令碼中心上的範例指令碼，請檢查：[https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)

3.  **Windows 檔案總管**   使用 Windows 檔案總管中要檢查的磁碟區上的磁碟空間，Lync Server 2013 記錄該儲存區與資料庫。

</div>

<span> </span>

</div>

</div>

</div>

