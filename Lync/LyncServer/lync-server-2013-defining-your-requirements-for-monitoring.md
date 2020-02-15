---
title: Lync Server 2013： 定義監控需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organizations's requirements for monitoring
ms:assetid: d587ff04-9af6-4ac1-ad42-076e7a40ac75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205284(v=OCS.15)
ms:contentKeyID: 48185491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a8f411b62aa1368600db21b59b4b009ca6df6c7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-monitoring-in-lync-server-2013"></a>定義 Lync Server 2013 中監視的需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-05_

簡化的部署和安裝監控 Microsoft Lync Server 2013 中也有精簡中定義監控您的組織需求的相關的程序。 不過，仍有幾個重要的問題，再開始安裝及設定 Lync Server 2013 應該解決：

**您想要監視哪些類型的資料？** Lync Server 2013 可讓您監視兩種不同類型的資料： 通話詳細記錄 (CDR) 和經驗品質 (QoE) 資料。 詳細通話記錄可讓您追蹤的 Lync Server 功能，例如 Voice over IP (VoIP) 通話; 使用方式立即訊息 (IM);檔案傳輸。音訊/視訊 (A / V) 會議;和應用程式共用工作階段。 此資訊可協助您知道正在使用 Lync Server 的功能 （以及哪些項目不），也會提供時正在使用這些功能的資訊。 經驗品質資料可讓您維持在您的組織，包括網路封包遺失數等事項中所做的音訊和視訊通話品質的記錄，背景雜音和數量 」 抖動 」 （封包延遲的差異）。

如果您選擇啟用在 Lync Server 2013，您可以啟用監視 CDR 和 QoE 監控監控，或者您可以選擇啟用監視同時停用其他類型的一種類型。 例如，假設您的使用者只使用立即訊息和檔案傳輸，並不會進行音訊或視訊呼叫。 在此情況下，可能會啟用 QoE 監控的一點原因。 同樣地，Lync Server 容易啟用及停用監控部署監控之後。 例如，您可能會選擇部署監控，但最初保留 QoE 監視已停用。 如果遇到問題的音訊或視訊通話開始您的使用者無法再啟用 QoE 監視，並使用該資料來協助您進行疑難排解並解決這些問題。

沒有特定的優點 （或缺點） 安裝在同一時間相對於安裝監控之後已安裝 Lync Server 安裝 Lync Server 監視。 記住一點是，在您安裝監控，您必須選取要裝載監控存放區中，後端電腦與支援的版本的 SQL Server 必須是安裝和設定該電腦上，才能使用該電腦的監控之前. 如果您已在電腦上安裝 SQL Server，而且該電腦已準備就緒可以安裝在您安裝 Lync Server 的同一時間監視。 如果您不需要準備的後端電腦然後您可以繼續進行安裝 Lync Server 本身，然後再安裝監控每當後端電腦已準備就緒。

**您要安裝監控時？** 監視可安裝及設定在同時安裝並設定 Lync Server 2013;Lync Server 部署精靈會提供您要關聯監控資料庫中的前端集區，在安裝期間的機會。 或者，您可以在其中安裝監控安裝 Lync Server 本身; 之後這可以是經由您的前端集區和伺服器關聯監控資料庫、 使用拓撲產生器]，然後再發行修改後的拓撲。

**您需要多少監控資料庫的後端？** 單一監控資料庫可支援數以萬計的使用者 （Microsoft Lync Server 2010，它預估組合監控和封存資料庫無法支援 240000 個使用者）。 此外，單一監控資料庫可供多個前端集區;如果貴組織中有三個前端集區您無法建立所有三個這些集區都關聯的相同的後端儲存區。

這些明白表示，對許多組織而言，資料庫容量時將無法決定因素決定後端監控資料庫所需的數目。 相反地，更重要的考量可能是網路速度。 假設您有三個前端集區，但這些集區的其中一個位於跨越慢速網路連線。 在此情況下，您可能想要使用這兩個監視資料庫： 一個要服務有良好的網路連線] 中，兩個集區的資料庫和服務以較慢的網路連線的集區不同的資料庫。

規劃您監視的基礎結構時您應該也考慮到 Lync Server 2013 支援使用的鏡像資料庫的帳戶。 「 資料庫鏡像 」 可讓您同時維護的資料庫，與位於不同伺服器上每個資料庫的兩個副本。 任何時間的資料已寫入至相同的資料也會寫入至鏡像資料庫的主要資料庫。 如果主要資料庫應該失敗或否則會變成無法使用，您可以 「 容錯移轉 」 至鏡像資料庫使用簡單的 Lync Server PowerShell 命令。 例如：

    Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"

這是進行規劃時很重要因為鏡像功能會讓您需要的資料庫數目： 每個主要資料庫除了您必須要做為鏡像的第二個資料庫。

**Lync Server 網站需要自己自訂的監控設定嗎？** 當您安裝 Lync Server 2013 您也可以安裝全域集合的 CDR 和 QoE 組態設定;這些全域集合可讓您將相同的 CDR 和 QoE 設定套用至整個組織。 在許多情況下，這將足夠： 通常-有時候您會想，說，能夠監視 CDR 啟用您的所有使用者。

不過，有時候也可能當您想要將不同的設定套用至不同的站台。 例如，或許是您想要使用 CDR 和 QoE 監視 Redmond 網站，但只能使用 CDR 監視都柏林網站中。 同樣地，您可能想要保留的 60 天的監視資料 Redmond 網站中，但只需要都柏林站台中，30 天的維護這類型的資料。 Lync Server 2013 可讓您在網站範圍; 建立不同的 CDR 和 QoE 組態設定集合可讓您以不同方式管理每個網站。 （這包括同時啟用和停用監視以及設定管理設定，例如多久資料會保留）。

請注意，您就可以讓此決策，部署監控之前或之後部署監控。 例如，您可以部署監控並使用通用設定]，以管理整個組織。 如果您稍後改變心意，您可以建立不同集合的設定，說，Redmond 網站，並再使用這些設定來管理 redmond 監視。 （永遠套用至網站範圍設定優先於套用在全域範圍設定。）如果您再次改變心意，您可以只刪除套用至 Redmond 網站的組態設定。 移除網站設定的集合時再設定全域集合會自動套用至該網站。

</div>

<span> </span>

</div>

</div>

</div>

