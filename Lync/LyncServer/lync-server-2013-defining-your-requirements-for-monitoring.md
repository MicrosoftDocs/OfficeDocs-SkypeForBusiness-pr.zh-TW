---
title: Lync Server 2013：定義監控需求
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
ms.openlocfilehash: 6f116fec331c252934c42e624c36813218d8f9ca
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504320"
---
# <a name="defining-your-requirements-for-monitoring-in-lync-server-2013"></a>在 Lync Server 2013 中定義您的監控需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-05_

簡化 Microsoft Lync Server 2013 中的監控部署與安裝，也簡化了定義組織的監控需求所需的處理常式。 不過，在您開始安裝和設定 Lync Server 2013 之前，仍然必須先解決一些重要的問題：

**您要監視的資料類型為何？** Lync Server 2013 可讓您監視兩種不同類型的資料：通話詳述錄製 (CDR) 資料和經驗品質 (QoE) 資料。 詳細通話記錄可讓您追蹤 Lync Server 功能（例如 Voice over IP (VoIP) 電話）的使用方式;立即訊息 (IM) ;檔案傳輸;音訊/視頻 (A/V) 會議;和應用程式共用會話。 此資訊可協助您瞭解哪些 Lync Server 功能正在使用 (及哪些功能未) ，也會提供這些功能的使用方式資訊。 經驗品質資料可讓您維護組織中所進行之音訊和影片的品質品質記錄，包括遺失的網路封包數目、背景雜訊，以及「抖動」 () 封包延遲中的差異。

如果您選擇在 Lync Server 2013 中啟用監控，您可以啟用 CDR 監控和 QoE 監視，也可以選擇啟用一種監控類型，而讓其他類型保持停用。 例如，假設您的使用者只使用立即訊息和檔案傳輸，也不會進行音訊或視頻通話。 在此情況下，可能不需要啟用 QoE 監視。 同樣地，Lync Server 也可讓您在部署監控後，輕鬆啟用及停用監控。 例如，您可以選擇部署監控，但在開始時仍會停用 QoE 監視。 如果您的使用者開始遇到音訊或視頻通話的問題，您可以啟用 QoE 監視，並使用該資料來協助您疑難排解及解決這些問題。

當您安裝 Lync Server 時，並不會有特別優點 (或缺點) 在安裝 lync server 之後安裝監視。 需要記住的一點是，在您安裝監控之前，您必須先選取一部電腦來裝載後端監控存放區，而且必須先在該電腦上安裝及設定 SQL Server 的支援版本，該電腦才可用於監視。 如果您已在電腦上安裝 SQL Server，而且該電腦已準備好供使用，則您可以在安裝 Lync Server 的同時安裝監視。 如果您沒有現成的後端電腦，您可以繼續自行安裝 Lync Server，然後在後端電腦準備好使用時安裝監視。

**您何時要安裝監控？** 您可以在安裝和設定 Lync Server 2013 的同時安裝和設定監視;Lync Server 部署嚮導可讓您有機會在安裝期間，將前端集區與監控資料庫產生關聯。 或者，您也可以在安裝 Lync Server 本身之後安裝監視;若要使用拓撲產生器，將前端集區與伺服器與監控資料庫產生關聯，然後發佈修訂的拓撲，即可完成此動作。

**您需要多少個後端監控資料庫？** 單一監控資料庫可支援成千上萬的使用者 (用於 Microsoft Lync Server 2010，據此估計，監控和封存的組合資料庫可支援240000使用者) 。 此外，多個前端集區也可以使用單一監控資料庫;如果您的組織中有三個前端集區，您可以將這三個集區與同一個後端存放區產生關聯。

這只是表示，對許多組織而言，資料庫容量不會是決定所需的後端監控資料庫數目的決定因素。 相反地，更重要的考慮可能是網路速度。 假設您有三個前端集區，但其中一個集區位於慢速網路連接。 在此情況下，您可能會想要使用兩個監視資料庫：一個資料庫用來服務于具有良好網路連線的兩個集區，另一個是以慢速網路聯機服務集區的資料庫。

規劃您的監控基礎結構時，您也應該考慮 Lync Server 2013 是否支援使用鏡像資料庫。 「資料庫鏡像」為您提供一種方式，讓您能夠同時維護兩個資料庫複本，而每個資料庫都位於不同的伺服器上。 任何時間資料會寫入至主資料庫，且相同的資料也會寫入鏡像資料庫。 如果主資料庫應該失敗或變得無法使用，您可以使用簡易的 Lync Server PowerShell 命令，將容錯移轉至鏡像資料庫。 例如：

    Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"

這對於規劃的目的很重要，因為鏡像會要求您加倍必要的資料庫數目：除了每個主資料庫之外，您還需要另一個資料庫作為鏡像。

**您的 Lync Server 網站需要自己的自訂監視設定嗎？** 當您安裝 Lync Server 2013 時，也會安裝 CDR 和 QoE 設定設定的全域集合;這些全域集合可讓您將相同的 CDR 和 QoE 設定套用至整個組織。 在許多情況下，這會是足夠的：您經常需要的時間，也就是說，您可以為所有的使用者啟用 CDR 監控。

不過，您有時也可能會想要將不同的設定套用至不同的網站。 例如，您可能想要在 Redmond 網站中使用 CDR 和 QoE 監控，但只在您的都柏林網站中使用 CDR 監控。 同樣地，您可能想要保留 Redmond 網站中60天的監控資料，但只需要在都柏林網站中維護這種資料類型30天。 Lync Server 2013 可讓您在網站範圍上建立個別的 CDR 集合及 QoE 設定設定;這可讓您以不同方式管理每個網站。  (這包括啟用和停用監控，以及設定管理設定，例如保留資料的時間。 ) 

請注意，您可以在部署監控之前或部署監控之後，加以決定。 例如，您可以部署監控，然後使用通用設定來管理整個組織。 如果您稍後變更主意，您可以為 Redmond 網站建立個別的設定集合，然後使用這些設定來管理 Redmond 的監控。 在網站範圍套用的 (設定，永遠優先于全域範圍內套用的設定。 ) 如果您再次變更主意，您可以直接刪除套用至 Redmond 網站的設定設定。 移除網站設定的集合後，全域設定集合便會自動套用至該網站。

</div>

<span> </span>

</div>

</div>

</div>

