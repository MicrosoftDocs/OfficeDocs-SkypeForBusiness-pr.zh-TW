---
title: Lync Server 2013： 範例 QoE 資料庫查詢
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sample QoE database queries
ms:assetid: 04e6bdd3-bbd1-47ca-8114-94a3db6beeeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398100(v=OCS.15)
ms:contentKeyID: 48183280
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d454f04d521324f51712a632a339617b259cde5e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sample-qoe-database-queries-in-lync-server-2013"></a><span data-ttu-id="48085-102">Lync Server 2013 中的範例 QoE 資料庫查詢</span><span class="sxs-lookup"><span data-stu-id="48085-102">Sample QoE database queries in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48085-103">_**主題上次修改日期：** 2012年-10-17_</span><span class="sxs-lookup"><span data-stu-id="48085-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="48085-104">本節包含經驗品質 (QoE) 資料庫的範例查詢。</span><span class="sxs-lookup"><span data-stu-id="48085-104">This section contains sample queries for the Quality of Experience (QoE) database.</span></span>

<span data-ttu-id="48085-105">使用下列範例取得音訊資料流的抖動和封包遺漏平均值。</span><span class="sxs-lookup"><span data-stu-id="48085-105">Use the following example to get the jitter and packet loss average for all audio streams.</span></span>

    select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream

<span data-ttu-id="48085-106">使用下列範例找出用於 Meeting 主控台的會議總數。</span><span class="sxs-lookup"><span data-stu-id="48085-106">Use the following example to find the total numbers of conferences that used Meeting Console.</span></span>

    select avg(ConversationalMOS)
    from SessionView s
    inner join MediaLineView m
    on s.ConferenceDateTime = m.ConferenceDateTime
       and s.SessionSeq = m.SessionSeq
       and m.MediaLineLabel = 0 -- audio media line
       and s.CallerUserAgentType = 4 -- Lync
       and s.CalleeUserAgentType = 4 -- Lync

<span data-ttu-id="48085-107">使用下列範例取得每一個擷取裝置的 ConversstionalMOS、SendingMOS 及 ListendingMOS。</span><span class="sxs-lookup"><span data-stu-id="48085-107">Use the following example to get ConversstionalMOS, SendingMOS and ListendingMOS per capture device.</span></span>

    select t.DeviceName as Device, count(*) as SampleNum, avg(ConversationalMOS) as ConversationalMOS, avg(SendListenMOS) SendingMOS, avg(RecvListenMOS) as ListendingMOS
    from
    (
       select m.CallerCaptureDev as DeviceName, m.ConferenceDateTime, m.SessionSeq, a.StreamID, m.ConversationalMOS,a.SendListenMOS, a.RecvListenMOS
       from MediaLineView m
       inner join AudioStream a
       on m.ConferenceDateTime = a.ConferenceDateTime
          and m.SessionSeq = a.SessionSeq
          and m.MediaLineLabel = 0
    
       union
    
       select m.CalleeCaptureDev as DeviceName, m.ConferenceDateTime, m.SessionSeq, a.StreamID, m.ConversationalMOS,a.SendListenMOS, a.RecvListenMOS
       from MediaLineView m
       inner join AudioStream a
       on m.ConferenceDateTime = a.ConferenceDateTime
          and m.SessionSeq = a.SessionSeq
          and m.MediaLineLabel = 0
    
    )as t
    group by t.DeviceName
    order by SampleNum desc

</div>

<span> </span>

</div>

</div>

</div>

