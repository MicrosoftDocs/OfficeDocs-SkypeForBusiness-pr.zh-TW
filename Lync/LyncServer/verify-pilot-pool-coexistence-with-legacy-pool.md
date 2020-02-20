---
title: 確認舊版集區與試驗集區共存
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7a1208dff6546243377d608fded62050756e0b6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>確認舊版集區與試驗集區共存

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-29_

部署試驗集區之後，您需要確認兩個集區共存所使用的系統管理工具來檢視的集區資訊。 Lync Server 2013 集區與舊版的集區，您必須使用 Lync Server 2013 控制台] 及 [拓撲產生器工具。

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a>確認 Lync Server 2013 服務已啟動

1.  從 Lync Server 2013 前端伺服器，瀏覽至 [系統管理工具]\\服務] 小程式。

2.  確認下列服務正在執行前端伺服器上：

**Lync Server 2013 服務**

![啟動 Lync Server 服務的清單](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "啟動 Lync Server 服務的清單")

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a>開啟 Lync Server 2013 控制台

從前端伺服器 Lync Server 2013 部署中，開啟 Lync Server 2013 控制台]，選取 [Lync Server 2010 集區。 重複此程序來開啟 Lync Server 2013 集區。

**開啟 Lync Server 2013 控制台**

![選取 [URL] 對話方塊](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "選取 [URL] 對話方塊")

<div>


> [!IMPORTANT]  
> 在 Lync Server 2013，您必須升級為 Silverlight 版本 5 才能使用 Lync Server Control Panel 的 Silverlight。



</div>

現在此拓撲包含 Lync Server 2010 和 Lync Server 2013 伺服器角色。

**Lync Server 2013 控制台拓撲頁面**

![Lync Server 控制台的拓撲] 頁面上](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server 控制台的拓撲] 頁面上")

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a>請勿嘗試在 Lync Server 2010 拓撲產生器] 中開啟拓撲

如果您嘗試開啟拓撲中使用 Lync Server 2010 拓撲產生器]，就會發生下列錯誤。 拓撲只能檢視使用 Lync Server 2013 拓撲產生器]。 Lync Server 2013 拓撲產生器必須用來建立 Lync Server 2013 和 Lync Server 2010 的集區。

**Lync Server 2010 拓撲產生器錯誤訊息**

![Lync Server 拓撲產生器] MMC 貼齊錯誤](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server 拓撲產生器] MMC 貼齊錯誤")

</div>

</div>

<span> </span>

</div>

</div>

</div>

