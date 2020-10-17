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
ms.openlocfilehash: 69caa96c6f0e49d472f13da11b34f7d199322184
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512180"
---
# <a name="qoe-reports-in-lync-server-2013"></a>在 Lync Server 2013 中 QoE 報告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-01_

<div>

## <a name="qoe-summarytrend-reports"></a>QoE 摘要/趨勢報表

QoE 摘要/趨勢報告可用於尋找一天的峰使用時間，並檢查媒體質量，以協助確保組織的網路資源足夠。 您的組織也可以使用報告中提供的眾多篩選器，隔離特定位置、用戶端和裝置類型及伺服器的效能號碼。

QoE 摘要/趨勢報告包含：

  - UC 對 UC 摘要/趨勢報告

  - PSTN 摘要/趨勢報告

  - 會議摘要/趨勢報告

</div>

<div>

## <a name="qoe-performance-reports"></a>QoE 效能報告

QoE 效能報告提供三個報告的詳細資訊，這些報告著重于轉送伺服器、A/V 會議伺服器及端點位置的 QoE 效能。

</div>

<div>

## <a name="mediation-server-performance-report"></a>轉送伺服器效能報告

轉送伺服器效能報告會列出在指定期間內，一或多個中繼所取得的計量。 整合通訊 (UC) 對轉送伺服器腿的計量，以及每個通話的轉送伺服器對閘道腿會分開報告。 使用此報告可比較組織的各種轉送伺服器的數量與效能。

針對每個轉送伺服器 (和每個呼叫腿) ，該報告會顯示下列專案：

  - 通話數目

  - 封包遺失

  - 來回時間

  - 抖動

  - MOS) 的平均觀點 (

  - 傳送 MOS

  - 聆聽 MOS

  - 網路 MOS

  - 網路 MOS 降級

  - 回復傳回

  - 信號層級

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a>A/V 會議伺服器效能報告

A/V 會議伺服器效能報告提供一或多個 A/V 會議伺服器在指定期間內取得的計量清單。 您可以使用此報告來比較組織的各種 A/V 會議伺服器的數量與效能。 您的組織也可以隔離報告，只顯示特定用戶端類型的經驗，例如 Lync 用戶端或 PSTN 用戶端。

針對每個 A/V 會議伺服器，報表會顯示下列專案：

  - 會議數目

  - 封包遺失

  - 來回時間

  - 抖動

  - MOS) 的平均觀點 (

  - 傳送 MOS

  - 聆聽 MOS

  - 網路 MOS

  - 網路 MOS 降級

  - 回復傳回

  - 信號層級

</div>

<div>

## <a name="location-based-performance-report"></a>以位置為基礎的效能報告

Location-Based 效能報告可提供網路位置清單，並針對每個位置顯示每個預先決定的品質範圍中的呼叫數目。 這份報告的目標是針對不同的位置提供大量組織通話的媒體質量深入瞭解，使您能夠識別出不良的位置，並在組織的不同位置查看不同的媒體質量等級。

顯示報表時，會顯示不同的計量表-您的組織決定要報告的每個度量各有一個資料表。 您可以從下列度量值中選擇此報告：

  - MOS) 的平均觀點 (

  - 網路 MOS

  - 網路 MOS 降級

  - 傳送 MOS

  - 聆聽 MOS

  - 封包遺失

  - 抖動

  - 延遲

</div>

</div>

<span> </span>

</div>

</div>

</div>

