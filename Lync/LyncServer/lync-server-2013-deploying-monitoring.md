---
title: Lync Server 2013：部署監視
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 584b99b6e5fad72a07a35b748ab9bafa4116701a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a>在 Lync Server 2013 中部署監視

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-12-17_

Microsoft Lync Server 2013 監視基礎結構的主要變更，從已棄用監視伺服器角色的情況開始。 您現在可以在每個前端伺服器上 collocated 監視服務，而不是個別的監視伺服器角色（通常是必要的組織，將專用電腦設定為充當監視伺服器）。 在其他專案中，這項變更有助於：

  - 減少實現 Lync Server 2013 時所需的伺服器角色數目。 在這種情況下，遞減監視伺服器的角色也能避免維護專用伺服器來進行監視，以減少成本。

  - 減少 Lync Server 設定和管理的複雜性。 在每個前端伺服器上自動 collocating 監視服務，您就不需要再安裝、設定及管理監視伺服器角色。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中，存檔伺服器角色也已被棄用。 就像監視服務一樣，Lync Server 2013 封存服務現已在每個前端伺服器上 collocated。 這只需要注意，因為監視和歸檔通常會共用相同的 SQL Server 資料庫實例。



</div>

正如您預期的，這些變更對監視服務的安裝與管理方式有很大的影響。 例如，因為已不存在監視伺服器角色，所以已從 Lync Server 拓撲建立器中移除 [監視伺服器] 節點;也就是說，這表示您將不會再使用拓撲建立器的新監視伺服器嚮導，將新的監視伺服器新增到您的拓撲。 （該嚮導已不存在）。相反地，您通常會透過完成下列兩個步驟來在拓撲內執行監視服務：

1.  當您設定新的 Lync 伺服器池時，同時啟用監視。 （在 Lync Server 2013 中，會針對每個池逐一啟用或停用監視）。請注意，您可以在不實際收集監視資料的情況下啟用對某個池的監視，在本檔的 [設定呼叫詳細資料記錄] 和 [經驗品質設定] 區段中說明的程式。

2.  將監視存放區（即監視資料庫）與新的池建立關聯。 請注意，單一監視存儲可以與多個池建立關聯。 根據您的註冊機構池中駐留的使用者數目而定，這表示您不需要為每個池設定個別的監視資料庫。 相反地，單一監視存放區可以由多個池使用。

雖然在您建立新的資料庫池的同時啟用監視通常是比較容易的，但是也可以建立一個已停用監視的新池。 如果您這樣做，您可以在稍後使用拓撲建立器來啟用服務： [拓撲建立器] 提供啟用或停用池監視的方式，或將池與不同的監視存放區建立關聯。 請記住，即使不再有監視伺服器角色，您仍需建立一或多個監視存儲：後端資料庫，用來儲存由監視服務收集的資料。 您可以使用 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012 來建立這些後端資料庫。

<div>


> [!NOTE]  
> 如果已針對某個池啟用監視，您可以停用收集監控資料的程式，而不需變更您的拓撲： Lync Server 管理命令介面提供一種方式，讓您可以停用（然後重新啟用）通話詳細資料錄製（CDR）或品質的體驗（QoE）資料收集。 如需詳細資訊，請參閱本檔的設定通話詳細資料錄製和體驗設定一節。



</div>

在 2013 Lync server 中進行監視的另一個重要增強功能，就是 Lync Server 監視報告現在支援 IPv6：使用 [IP 位址] 欄位的報表會顯示 IPv4 或 IPv6 位址（視：1）所使用的 SQL 查詢;與，2） IPv6 位址儲存在監視資料庫中的位置。

<div>


> [!NOTE]  
> 確定 SQL Server Agent 服務啟動類型為 [自動]，且 SQL Server Agent 服務正在針對擁有監視資料庫的 SQL 實例執行，因此預設的監視 SQL Server 維護作業可以依排程的方式執行[SQL Server 代理程式服務] 的控制權。



</div>

本檔會逐步引導您完成安裝和設定 Lync Server 2013 的監視及監視報告的程式。 本檔提供可協助您執行下列逐步指示：

  - 在拓撲中啟用監視，並將監視存放區與前端池建立關聯。

  - 安裝 SQL Server Reporting Services 和 Lync Server Monitoring 報告。 監視報告是預先配置的報告，可為監視資料庫中儲存的資訊提供不同的視圖。

  - 設定通話詳細資料錄製（CDR）和體驗品質（QoE）資料收集。 通話詳細資料錄製提供一種方式，讓您追蹤 Lync 伺服器功能（例如，語音 over IP 通話）的使用方式;立即訊息（IM）;檔案傳輸;音訊/視頻（A/V）會議;與應用程式共用會話。 QoE 度量單位會追蹤您組織中的音訊和視頻通話品質，包括網路資料包遺失、背景雜色及「抖動」（資料包延遲的差異）等專案。

  - 從監視資料庫手動清除 CDR 和/或 QoE 記錄。

</div>

<span> </span>

</div>

</div>

</div>

