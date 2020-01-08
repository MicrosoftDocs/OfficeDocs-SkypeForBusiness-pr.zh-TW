---
title: Lync Server 2013：定義監控需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organizations's requirements for monitoring
ms:assetid: d587ff04-9af6-4ac1-ad42-076e7a40ac75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205284(v=OCS.15)
ms:contentKeyID: 48185491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7a81f83cddca46a50f84fb20785a59b20a3db78
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-monitoring-in-lync-server-2013"></a>在 Lync Server 2013 中定義監控需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-05_

在 Microsoft Lync Server 2013 中簡化監視的部署和安裝，也可簡化定義貴組織的監視需求所涉及的程式。 不過，在您開始安裝及設定 Lync Server 2013 之前，仍需要解決幾個主要問題：

**您想要監視何種類型的資料？** Lync Server 2013 可讓您監視兩種不同類型的資料：通話詳細錄製（CDR）資料和體驗品質（QoE）資料。 通話詳細資料錄製提供一種方式，讓您追蹤 Lync Server 功能（例如，語音 over IP 通話）的使用方式;立即訊息（IM）;檔案傳輸;音訊/視頻（A/V）會議;與應用程式共用會話。 這項資訊可協助您瞭解所使用的是哪些 Lync Server 功能（以及哪些功能不是），也會提供這些功能的使用方式的相關資訊。 經驗品質資料可讓您維護貴組織中音訊和視頻通話品質的記錄，包括網路資料包遺失、背景雜色及「抖動」（資料包延遲的差異）等專案。

如果您選擇在 Lync Server 2013 中啟用監視，您可以同時啟用 CDR 監視與 QoE 監視，或者，您也可以選擇啟用單一監視類型，而讓其他類型保持停用。 例如，假設您的使用者只使用立即訊息和檔案傳輸，且不進行音訊或視頻通話。 在這種情況下，可能無需啟用 QoE 監視。 同樣地，Lync Server 可讓您輕鬆啟用並在部署監視後停用監視。 例如，您可以選擇部署監視，但不停停 QoE 監視。 如果您的使用者開始遇到音訊或視頻通話的問題，您可以啟用 QoE 監視，並使用該資料來協助您疑難排解並解決這些問題。

在安裝 Lync Server 之後，沒有特殊的優點（或缺點），無法安裝 [在 Lync Server 安裝後進行監視] 與 [安裝]。 要記住的一點是，在您安裝監視之前，您必須先選取電腦來託管後端監視存放區，而且在該電腦上必須安裝並設定受支援版本的 SQL Server，才能使用該電腦進行監視. 如果您已在電腦上安裝 SQL Server，且該電腦已準備好使用，您可以在安裝 Lync Server 的同時安裝監視。 如果您沒有已準備好的後端電腦，您可以繼續自行安裝 Lync Server，然後在後端電腦準備好使用時安裝監視。

**您何時要安裝監視？** 您可以在安裝和設定 Lync Server 2013 的同時安裝和設定監視;Lync Server 部署嚮導會提供機會，讓您在安裝期間將前端池與監視資料庫建立關聯。 或者，您也可以在安裝 Lync Server 本身之後安裝監視;您可以使用拓撲建立器，將前端池和伺服器與監視資料庫建立關聯，然後發佈已修改的拓撲。

**您需要多少個後端監視資料庫？** 單一監視資料庫可支援數十個使用者（針對 Microsoft Lync Server 2010，據估計，在監視與封存中，collocated 資料庫可支援240000使用者）。 此外，單一監視資料庫可由多個前端池使用;如果您的組織有三個前端池，您可以將這三個池與同一個後端書店建立關聯。

這只意味著，對於許多組織而言，資料庫容量不會是決定所需後端監視資料庫數目的決定因素。 相反地，更重要的考慮因素可能是網路速度。 假設您有三個前端池，但是其中一個池是在緩慢的網路連線中找到。 在這種情況下，您可能會想要使用兩個監視資料庫：一個資料庫以使用良好的網路連線來為兩個池提供服務，並使用一個單獨的資料庫，以較慢的網路連線提供該池的服務。

規劃您的監視基礎結構時，您也應該考慮 Lync Server 2013 支援使用鏡像資料庫的情況。 「資料庫鏡像」可讓您同時維護資料庫的兩份複本，並讓每個資料庫都駐留在不同的伺服器上。 任何時候，都會將資料寫入到主要資料庫，而這種資料也會寫入到鏡像資料庫中。 如果主資料庫應該失敗或無法使用，您可以使用簡單的 Lync Server PowerShell 命令，將 [容錯移轉] 到鏡像資料庫。 例如：

    Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"

這對於規劃的目的非常重要，因為鏡像會要求您將所需的資料庫數加倍：除了每個主資料庫之外，您還需要第二個資料庫作為鏡像。

**您的 Lync Server 網站需要自己的自訂監視配置嗎？** 當您安裝 Lync Server 2013 時，您也會安裝 [CDR] 和 [QoE 設定] 的全域集合;這些全域集合讓您能夠將相同的 CDR 與 QoE 設定套用到整個組織。 在許多情況下，這會足夠：您通常會想要為所有的使用者啟用 CDR 監視。

不過，您也可能會想要將不同的設定套用至不同的網站。 例如，您可能想要在雷德蒙網站中使用 CDR 與 QoE 監視，但只在您的都柏林網站中使用 CDR 監視。 同樣地，您可能想要在雷德蒙者網站保留60天的監控資料，但只需要在都柏林網站中維護此類型的資料。 Lync Server 2013 可讓您在網站範圍中建立不同的 CDR 及 QoE 設定設定;這可讓您以不同方式管理每個網站。 （這包括啟用和停用監控，以及設定管理設定，例如要保留多久資料。）

請注意，您可以在部署監視之前或在部署監視之後進行此決策。 例如，您可以部署監視，然後使用 [全域設定] 管理整個組織。 如果您稍後改變主意，您可以針對雷德蒙者的網站建立一組不同的設定，然後使用這些設定來管理雷德蒙者的監視。 （在網站範圍套用的設定，總是優先于在全域範圍中套用的設定。）如果您再次改變主意，您可以直接刪除套用至雷蒙德網站的設定設定。 移除網站設定的集合之後，全域設定集合就會自動套用到該網站。

</div>

<span> </span>

</div>

</div>

</div>

