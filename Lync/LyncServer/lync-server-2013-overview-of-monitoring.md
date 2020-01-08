---
title: Lync Server 2013：監視的概覽
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88bfb8170b2334c322c612628daa1f8b9db2473c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a>Lync Server 2013 中的監控概覽

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-05_

在 Microsoft Lync Server 2013 中，[監視] 可用來收集使用方式資訊，以及有關使用者所涉及之通訊會話的體驗品質（QoE）資料。 會話是一般的詞彙，涵蓋使用者與 a 的連線：

  - 會議

  - 會議模態（例如音訊/視頻或應用程式共用）

  - 透過對等交談（例如立即訊息或語音通話）的另一個使用者

<div>


> [!NOTE]  
> Lync Server 2013 會追蹤每個會話的相關資訊：稱為誰;會話中使用了哪些端點;此會話的持續時間為多久;會話的感知品質為何;等等。 不過，Lync Server 不會錄製並儲存實際通話本身。 這也包括立即訊息會話：雖然 Lync Server 會記錄立即訊息會話的相關資訊，但不會保留在會話期間傳送的每一條立即訊息的記錄。



</div>

Lync Server 收集的通話詳細資訊可用於任何數量的用途，包括：

  - **投資回報率（ROI）**。 系統管理員可以將監視伺服器所收集的使用資料與針對其先前的電話系統所收集的類似資料進行比較，以顯示成本節約，並協助論證 Lync Server 的部署。

  - **裝置庫存管理**。 資產管理資訊可協助系統管理員識別仍在使用中的舊裝置，這些裝置需要進行取代，以及找出目前不會使用的昂貴裝置。

  - 技術支援人員。 疑難排解資料可讓支援工程師判斷使用者撥打電話失敗的原因，而不需收集伺服器或用戶端記錄就能這麼做。 針對沒有 Microsoft Lync 2013 和 Lync Server 2013 深入技術知識的支援人員，您可以輕鬆存取和理解此資訊。

  - **系統疑難排解**。 讓系統管理員能夠偵測到可能造成使用者無法執行基本工作（例如加入會議、建立通話或傳送立即訊息）的主要問題。

除了這項基本的呼叫資訊之外，監視伺服器也提供允許 SIP 端點（例如 Lync 2013）提供伺服器不需要存取的疑難排解資訊的機制：

  - **影響品質的媒體度量**單位。 這些度量單位會涉及來電本身的實際傳輸;也就是說，它們會將旅遊記錄分類提供給網路上的呼叫 journeys。 這些標準（包括資料包遺失、抖動及往返行程時間等）提供從您的端點移至它到達其他人終點所需時間之呼叫的相關資訊。

  - **向最終使用者報告的問題**。 這些指標包括在電腦上的其他程式無法使用的情況下，Lync 2013 的 [Lync] 提供給最終使用者的品質較差、說話太柔、網路連線較差或品質不佳的情況。使用可用的資源。

  - **環境資訊**。 這些指標詳細說明通話品質因素，例如使用麥克風與喇叭類型、使用者是否透過 VPN 連線，以及使用者是否在無線連線。

在每個通話結束時，SIP 相容端點會自動將此資訊傳送到主持呼叫的前端伺服器。 您不需要執行任何動作，即可取得端點以傳送該資訊;該行為是在 SIP 通訊協定內建。 不過，如果您想要收集並儲存該資訊，您必須安裝並啟用監視。 如果您已安裝並啟用監視，則呼叫資訊是由在前端伺服器上執行並中繼到一組 SQL Server 資料庫的代理程式所收集。

請注意，在 Lync Server 2013 中已簡化安裝和設定監視的程式。 在舊版的軟體中，監視需要個別的監視伺服器角色，這通常是專門用來做為監視伺服器的個別電腦。 但在 Lync Server 2013 中，已消除監視伺服器角色。 相反地，監視服務（以「整合資料收集代理程式」的形式）已 collocated 到所有前端伺服器。 這至少有兩個主要優點。 監視服務的 Collocation：

  - 減少實現 Lync Server 2013 時所需的伺服器角色數目。 遞減監視伺服器角色也能避免維護專用伺服器以進行監視，以協助降低成本。

  - 減少 Lync Server 2013 設定和管理的複雜性。 在每個前端伺服器上 collocating [監視服務]，您就不需要再安裝、設定及管理監視伺服器角色。

如需詳細資訊，請參閱 Lync Server 2013 2013 部署指南中的在[Lync server 2013 中部署監視](lync-server-2013-deploying-monitoring.md)主題。

</div>

<span> </span>

</div>

</div>

</div>

