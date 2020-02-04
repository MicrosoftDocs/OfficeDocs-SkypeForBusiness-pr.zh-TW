---
title: Lync Server 2013： QoE 查看詳細資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE view details
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49733677
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d47fb90b7ffb9eb0cb7fcd1631a0f00ca249276a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-view-details-in-lync-server-2013"></a><span data-ttu-id="a7c50-102">QoE Lync Server 2013 中的 [查看詳細資料]</span><span class="sxs-lookup"><span data-stu-id="a7c50-102">QoE view details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7c50-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="a7c50-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="a7c50-104">[視圖] 涵蓋從 QoE SQL 資料庫傳回資料最常見的案例。</span><span class="sxs-lookup"><span data-stu-id="a7c50-104">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="a7c50-105">它是用來建立自訂報表的建議視圖，而不是直接存取資料庫資料表;這是因為視圖更可能會維持與未來版本的向後相容性。</span><span class="sxs-lookup"><span data-stu-id="a7c50-105">It is recommended views used for building custom reports instead of directly accessing the database tables; that’s because views are more likely to maintain backwards compatibility with future releases.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7c50-106">[視圖名稱]</span><span class="sxs-lookup"><span data-stu-id="a7c50-106">View Name</span></span></th>
<th><span data-ttu-id="a7c50-107">說明</span><span class="sxs-lookup"><span data-stu-id="a7c50-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7c50-108"><a href="lync-server-2013-audiostreamdetail-view.md">Lync Server 2013 中的 [AudioStreamDetail] 視圖</a></span><span class="sxs-lookup"><span data-stu-id="a7c50-108"><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a7c50-109">儲存資料庫中每個音訊資料流程的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a7c50-109">Stores information about each audio stream in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7c50-110"><a href="lync-server-2013-medialine-view.md">Lync Server 2013 中的 [MediaLine] 視圖</a></span><span class="sxs-lookup"><span data-stu-id="a7c50-110"><a href="lync-server-2013-medialine-view.md">MediaLine view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a7c50-111">儲存資料庫中每個媒體線的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a7c50-111">Stores information about each media line in the database.</span></span> <span data-ttu-id="a7c50-112">一個音訊會話通常包含一個音訊媒體線。</span><span class="sxs-lookup"><span data-stu-id="a7c50-112">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="a7c50-113">一個音訊與影片（A/V）會話通常包含一個音訊媒體線和一個影片媒體線;不過，如果使用會議裝置或使用圖庫視圖，該會話可能會包含兩個視頻媒體線。</span><span class="sxs-lookup"><span data-stu-id="a7c50-113">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7c50-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">Lync Server 2013 中的 [NetworkConfigurationSettings] 視圖</a></span><span class="sxs-lookup"><span data-stu-id="a7c50-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a7c50-115">儲存網路設定的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a7c50-115">Stores information about the network configuration.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7c50-116"><a href="lync-server-2013-session-view.md">Lync Server 2013 中的 [會話] 視圖</a></span><span class="sxs-lookup"><span data-stu-id="a7c50-116"><a href="lync-server-2013-session-view.md">Session view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a7c50-117">儲存在資料庫中有記錄的會話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a7c50-117">Stores information about sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7c50-118"><a href="lync-server-2013-useragent-view.md">Lync Server 2013 中的 [UserAgent] 視圖</a></span><span class="sxs-lookup"><span data-stu-id="a7c50-118"><a href="lync-server-2013-useragent-view.md">UserAgent view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a7c50-119">儲存在資料庫中有記錄的會話中所涉及之使用者代理程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a7c50-119">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7c50-120"><a href="lync-server-2013-videostreamdetail-view.md">Lync Server 2013 中的 [VideoStreamDetail] 視圖</a></span><span class="sxs-lookup"><span data-stu-id="a7c50-120"><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a7c50-121">儲存資料庫中每個影片資料流程的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a7c50-121">Stores information about each video stream in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

