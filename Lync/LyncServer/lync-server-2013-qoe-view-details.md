---
title: Lync Server 2013： QoE 查看詳細資料
description: Lync Server 2013： QoE 查看詳細資料。
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
ms.openlocfilehash: b20eb083295a5f3d3ecb5be7a8c96d9c4b7cfab2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579099"
---
# <a name="qoe-view-details-in-lync-server-2013"></a><span data-ttu-id="f3bde-103">在 Lync Server 2013 中 QoE 查看詳細資料</span><span class="sxs-lookup"><span data-stu-id="f3bde-103">QoE view details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3bde-104">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="f3bde-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="f3bde-105">檢視涵蓋從 QoE SQL 資料庫傳回資料時最常見的案例。</span><span class="sxs-lookup"><span data-stu-id="f3bde-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="f3bde-106">此為建議的檢視，可用來建立自訂報告，而非直接存取資料庫資料表；那是因為檢視較可能維持與日後版本的回溯相容性。</span><span class="sxs-lookup"><span data-stu-id="f3bde-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that’s because views are more likely to maintain backwards compatibility with future releases.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3bde-107">檢視名稱</span><span class="sxs-lookup"><span data-stu-id="f3bde-107">View Name</span></span></th>
<th><span data-ttu-id="f3bde-108">描述</span><span class="sxs-lookup"><span data-stu-id="f3bde-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3bde-109"><a href="lync-server-2013-audiostreamdetail-view.md">Lync Server 2013 中的 AudioStreamDetail 視圖</a></span><span class="sxs-lookup"><span data-stu-id="f3bde-109"><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3bde-110">儲存資料庫中每個音訊資料流的資訊。</span><span class="sxs-lookup"><span data-stu-id="f3bde-110">Stores information about each audio stream in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3bde-111"><a href="lync-server-2013-medialine-view.md">Lync Server 2013 中的 MediaLine 視圖</a></span><span class="sxs-lookup"><span data-stu-id="f3bde-111"><a href="lync-server-2013-medialine-view.md">MediaLine view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3bde-112">儲存資料庫中每個媒體行的資訊。</span><span class="sxs-lookup"><span data-stu-id="f3bde-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="f3bde-113">一個音訊工作階段通常包含一個音訊媒體行。</span><span class="sxs-lookup"><span data-stu-id="f3bde-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="f3bde-114">一個音訊和視訊 (A/V) 工作階段通常包含一個音訊媒體行和一個視訊媒體行；不過，如果使用會議裝置或使用圖庫檢視，則工作階段可能包含兩個媒體行。</span><span class="sxs-lookup"><span data-stu-id="f3bde-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3bde-115"><a href="lync-server-2013-networkconfigurationsettings-view.md">Lync Server 2013 中的 NetworkConfigurationSettings 視圖</a></span><span class="sxs-lookup"><span data-stu-id="f3bde-115"><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3bde-116">儲存網路設定的資訊。</span><span class="sxs-lookup"><span data-stu-id="f3bde-116">Stores information about the network configuration.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3bde-117"><a href="lync-server-2013-session-view.md">Lync Server 2013 中的會話視圖</a></span><span class="sxs-lookup"><span data-stu-id="f3bde-117"><a href="lync-server-2013-session-view.md">Session view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3bde-118">儲存在資料庫中擁有記錄之工作階段的資訊。</span><span class="sxs-lookup"><span data-stu-id="f3bde-118">Stores information about sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3bde-119"><a href="lync-server-2013-useragent-view.md">Lync Server 2013 中的 UserAgent 視圖</a></span><span class="sxs-lookup"><span data-stu-id="f3bde-119"><a href="lync-server-2013-useragent-view.md">UserAgent view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3bde-120">儲存使用者代理程式的資訊，這些使用者代理程式與在資料庫中擁有記錄的工作階段相關。</span><span class="sxs-lookup"><span data-stu-id="f3bde-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3bde-121"><a href="lync-server-2013-videostreamdetail-view.md">Lync Server 2013 中的 VideoStreamDetail 視圖</a></span><span class="sxs-lookup"><span data-stu-id="f3bde-121"><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3bde-122">儲存在資料庫中每個視訊資料流的資訊。</span><span class="sxs-lookup"><span data-stu-id="f3bde-122">Stores information about each video stream in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

