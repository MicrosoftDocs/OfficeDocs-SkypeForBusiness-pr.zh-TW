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
ms.openlocfilehash: 6bba917427e42dcba689d3b248c7d889c798368f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512160"
---
# <a name="qoe-view-details-in-lync-server-2013"></a><span data-ttu-id="cb5c1-102">在 Lync Server 2013 中 QoE 查看詳細資料</span><span class="sxs-lookup"><span data-stu-id="cb5c1-102">QoE view details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb5c1-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="cb5c1-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="cb5c1-104">檢視涵蓋從 QoE SQL 資料庫傳回資料時最常見的案例。</span><span class="sxs-lookup"><span data-stu-id="cb5c1-104">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="cb5c1-105">此為建議的檢視，可用來建立自訂報告，而非直接存取資料庫資料表；那是因為檢視較可能維持與日後版本的回溯相容性。</span><span class="sxs-lookup"><span data-stu-id="cb5c1-105">It is recommended views used for building custom reports instead of directly accessing the database tables; that’s because views are more likely to maintain backwards compatibility with future releases.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb5c1-106">檢視名稱</span><span class="sxs-lookup"><span data-stu-id="cb5c1-106">View Name</span></span></th>
<th><span data-ttu-id="cb5c1-107">描述</span><span class="sxs-lookup"><span data-stu-id="cb5c1-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb5c1-108"><a href="lync-server-2013-audiostreamdetail-view.md">Lync Server 2013 中的 AudioStreamDetail 視圖</a></span><span class="sxs-lookup"><span data-stu-id="cb5c1-108"><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cb5c1-109">儲存資料庫中每個音訊資料流的資訊。</span><span class="sxs-lookup"><span data-stu-id="cb5c1-109">Stores information about each audio stream in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb5c1-110"><a href="lync-server-2013-medialine-view.md">Lync Server 2013 中的 MediaLine 視圖</a></span><span class="sxs-lookup"><span data-stu-id="cb5c1-110"><a href="lync-server-2013-medialine-view.md">MediaLine view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cb5c1-111">儲存資料庫中每個媒體行的資訊。</span><span class="sxs-lookup"><span data-stu-id="cb5c1-111">Stores information about each media line in the database.</span></span> <span data-ttu-id="cb5c1-112">一個音訊工作階段通常包含一個音訊媒體行。</span><span class="sxs-lookup"><span data-stu-id="cb5c1-112">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="cb5c1-113">一個音訊和視訊 (A/V) 工作階段通常包含一個音訊媒體行和一個視訊媒體行；不過，如果使用會議裝置或使用圖庫檢視，則工作階段可能包含兩個媒體行。</span><span class="sxs-lookup"><span data-stu-id="cb5c1-113">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb5c1-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">Lync Server 2013 中的 NetworkConfigurationSettings 視圖</a></span><span class="sxs-lookup"><span data-stu-id="cb5c1-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cb5c1-115">儲存網路設定的資訊。</span><span class="sxs-lookup"><span data-stu-id="cb5c1-115">Stores information about the network configuration.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb5c1-116"><a href="lync-server-2013-session-view.md">Lync Server 2013 中的會話視圖</a></span><span class="sxs-lookup"><span data-stu-id="cb5c1-116"><a href="lync-server-2013-session-view.md">Session view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cb5c1-117">儲存在資料庫中擁有記錄之工作階段的資訊。</span><span class="sxs-lookup"><span data-stu-id="cb5c1-117">Stores information about sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb5c1-118"><a href="lync-server-2013-useragent-view.md">Lync Server 2013 中的 UserAgent 視圖</a></span><span class="sxs-lookup"><span data-stu-id="cb5c1-118"><a href="lync-server-2013-useragent-view.md">UserAgent view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cb5c1-119">儲存使用者代理程式的資訊，這些使用者代理程式與在資料庫中擁有記錄的工作階段相關。</span><span class="sxs-lookup"><span data-stu-id="cb5c1-119">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb5c1-120"><a href="lync-server-2013-videostreamdetail-view.md">Lync Server 2013 中的 VideoStreamDetail 視圖</a></span><span class="sxs-lookup"><span data-stu-id="cb5c1-120"><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="cb5c1-121">儲存在資料庫中每個視訊資料流的資訊。</span><span class="sxs-lookup"><span data-stu-id="cb5c1-121">Stores information about each video stream in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

