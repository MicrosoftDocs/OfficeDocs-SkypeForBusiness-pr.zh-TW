---
title: 驗證試驗集區與舊版集區共存
description: 請確認試驗集區與舊版集區共存。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b910939b59fdaed6df32ae504eb2719435a0161e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555549"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>驗證試驗集區與舊版集區共存

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-29_

部署試驗集區之後，您必須使用系統管理工具來查看集區資訊，以確認兩個集區共存。 對於 Lync Server 2013 集區和舊版集區，您必須使用 Lync Server 2013 控制台和拓撲產生器工具。

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a>確認已啟動 Lync Server 2013 服務

1.  從 Lync Server 2013 前端伺服器，流覽至 [系統管理工具 \\ 服務] 小程式。

2.  確認下列服務正在前端伺服器上執行：

**Lync Server 2013 服務**

![已啟動的 Lync Server 服務清單](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "已啟動的 Lync Server 服務清單")

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a>開啟 Lync Server 2013 控制台

在 Lync Server 2013 部署中的前端伺服器上，開啟 [Lync Server 2013 控制台]，然後選取 [Lync Server 2010 集區]。 重複此程式以開啟 Lync Server 2013 集區。

**開啟 Lync Server 2013 控制台**

![[選取 URL] 對話方塊](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "[選取 URL] 對話方塊")

<div>


> [!IMPORTANT]  
> 在 Lync Server 2013 上，您必須在使用 Lync Server 控制台之前，將 Silverlight 升級至 Silverlight 第5版。



</div>

此拓撲現在包括 Lync Server 2010 和 Lync Server 2013 伺服器角色。

**Lync Server 2013 控制台拓撲頁面**

![Lync Server 控制台-拓撲頁面](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server 控制台-拓撲頁面")

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a>不要嘗試在 Lync Server 2010 拓撲產生器中開啟拓撲

如果您嘗試使用 Lync Server 2010 拓撲產生器來開啟拓撲，您會遇到下列錯誤。 拓撲只能以 Lync Server 2013 拓撲產生器來查看。 Lync Server 2013 拓撲產生器必須用來建立 Lync Server 2013 和 Lync Server 2010 的集區。

**Lync Server 2010 拓撲產生器錯誤訊息**

![Lync Server 拓撲產生器 MMC 貼齊錯誤](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server 拓撲產生器 MMC 貼齊錯誤")

</div>

</div>

<span> </span>

</div>

</div>

</div>

