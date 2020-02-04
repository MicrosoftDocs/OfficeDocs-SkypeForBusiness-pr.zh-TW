---
title: Lync Server 2013： QoE 報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE reports
ms:assetid: 49c827af-b8dd-4c6e-b0dc-b4bc6d60e9a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720913(v=OCS.15)
ms:contentKeyID: 63969601
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9eead17e9cd08267f941d80cb25460f4d456d896
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a>在 Lync Server 2013 中 QoE 報表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-01_

<div>

## <a name="qoe-summarytrend-reports"></a>QoE 摘要/趨勢報表

QoE 摘要/趨勢報告可用於找出一天的高峰使用時間，並在這些時間檢查媒體質量，以協助確保貴組織的網路資源足夠。 貴組織也可以使用報告中提供的許多篩選器，來隔離特定位置、用戶端和裝置類型以及伺服器的效能數。

QoE 摘要/趨勢報表包括：

  - UC 與 UC 摘要/趨勢報告

  - PSTN 摘要/趨勢報告

  - 會議摘要/趨勢報表

</div>

<div>

## <a name="qoe-performance-reports"></a>QoE 效能報告

QoE 效能報告提供三筆報表的詳細資料，集中精力集中在中繼伺服器、A/V 會議伺服器及端點位置的 QoE 效能。

</div>

<div>

## <a name="mediation-server-performance-report"></a>中繼伺服器效能報告

[採集轉送伺服器效能] 報告會列出在指定期間內由一或多個轉送器所達到的指標。 整合通訊（UC）到轉送伺服器腿的度量值，以及每個通話的中繼伺服器對閘道腿都是分開報告的。 使用此報告來比較貴組織不同中繼伺服器的數量與效能。

針對每個中繼伺服器（以及每個通話腿），報告會顯示下列內容：

  - 通話次數

  - 資料包遺失

  - 往返行程時間

  - 抖動

  - 會話平均觀念（MOS）

  - 傳送 MOS

  - 聆聽 MOS

  - Network MOS

  - 網路 MOS 下降

  - 回顯傳回

  - 信號電平

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a>A/V 會議伺服器效能報告

A/V 會議伺服器效能報告提供在指定的時段內，一或多個 A/V 會議伺服器所達到的度量單位清單。 此報告可用來比較貴組織的各種 A/V 會議伺服器的音量與效能。 您的組織也可以隔離報告，只顯示特定用戶端類型的體驗，例如 Lync 用戶端或 PSTN 用戶端。

針對每個 A/V 會議伺服器，報告會顯示下列內容：

  - 會議數量

  - 資料包遺失

  - 往返行程時間

  - 抖動

  - 會話平均觀念（MOS）

  - 傳送 MOS

  - 聆聽 MOS

  - Network MOS

  - 網路 MOS 下降

  - 回顯傳回

  - 信號電平

</div>

<div>

## <a name="location-based-performance-report"></a>以位置為基礎的效能報告

以位置為基礎的效能報告會提供網路位置清單，並針對每個位置顯示每個預先確定的品質範圍中的呼叫數目。 此報告的目的是為了深入瞭解貴組織的各種位置電話通話的媒體質量，讓您能夠找出較差的位置，並查看貴組織中不同的媒體質量等級。不同的位置。

顯示報表時，會顯示不同的度量資料表：針對貴組織決定要報告的每個指標，一個資料表。 您可以從下列度量單位選擇此報告：

  - 會話平均觀念（MOS）

  - Network MOS

  - 網路 MOS 下降

  - 傳送 MOS

  - 聆聽 MOS

  - 資料包遺失

  - 抖動

  - 遲滯

</div>

</div>

<span> </span>

</div>

</div>

</div>

