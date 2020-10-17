---
title: Lync Server 2013：大型會議支援常見問題
description: Lync Server 2013：大型會議支援常見問題。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8d206400b46fc32a3af7b21ad7d50663e85d069
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557549"
---
# <a name="large-meeting-support-faq-for-lync-server-2013"></a>Lync Server 2013 的大型會議支援常見問題

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

下列各節提供建立與舉行大型會議的常見問題解答。

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a>問：大型會議中可以有多少使用者參與？

Lync Server 使用者模型會在專用於大型會議的集區中指定共用集區或1000使用者中的250使用者限制，但這些號碼只代表我們所測試的使用者人數，而且只代表我們用於測試的特定硬體集。 我們是根據測試來建議這些大小上限的限制。 不過，您可以在您的組織中，透過設定一或多個會議原則 (，使用 Lync Server 管理命令介面中的 Windows PowerShell 指令程式，或使用 Lync Server 控制台) 來控制實際的參與者人數。 您在會議原則中指定的數目可以是介於 1 和 4,294,967,295 之間的任一個 32 位元整數，但建議的人數為 2 到 250 (含) 位參與者；預設值為 250。

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a>問：在大型會議專屬的集區中可以有多少個會議或其他工作負載？

若要在最多 1000 位參與者的大型會議中確保最佳使用者經驗，建議在大型會議專屬的集區中一次僅舉行單一大型會議。同時建議當大型會議正在進行時，不要允許任何其他工作負載於該集區上執行。

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a>問：大型會議的召集人應該位於專屬集區中嗎？

否。除了專門管理大型會議排程的員工之外，建議不要讓任何其他使用者位於專屬集區中。這樣可以防止其他即時通訊流量導致集區中所舉行的大型會議發生問題。您應該使用大型會議排程員工的使用者帳戶，在專屬集區中排程大型會議。您應該將會議召集人 (申請大型會議的使用者) 的使用者帳戶新增為大型會議的主持人。

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a>問：我可以在大型會議中使用哪些媒體形式？

最多含有 1000 位使用者的大型會議可以包含音訊、視訊、PowerPoint 共用、 白板及目前狀態輪詢。

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a>問：我可以在大型會議中使用群組立即訊息 (IM) 嗎？

是。 但是，大量的立即訊息 (特別是在大量與會者進行傳送時) 會因為在 IM 視窗中快速捲動文字的問題而影響到使用者經驗。 將大量立即訊息傳遞給最多 1000 位使用者也會引發顯著的伺服器負載，這會影響到效能。 一般來說，只有問題和解答 (Q 為) 時，才需要 IM \& 。

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a>使用者可以從電話撥入來加入大型會議嗎？

是。 如果已正確部署 Lync Server 2013 集區，且已啟用電話撥入式會議，使用者將可以撥號加入大型會議。 我們的測試顯示 1000 位使用者中最多有 15% 的使用者可以在 10 分鐘內加入大型會議。

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a>問：我可以在虛擬拓撲中舉行大型會議嗎？

我們尚未在虛擬拓撲中測試過大型會議，因此，不支援使用虛擬機器來裝載適用於大型會議的專屬集區。

</div>

</div>

<span> </span>

</div>

</div>

</div>

