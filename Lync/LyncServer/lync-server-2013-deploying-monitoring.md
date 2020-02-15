---
title: Lync Server 2013： 部署監控
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73b9947cf77df8d0c3baedcb27d8e13cc728e52b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a>部署 Lync Server 2013 中監視

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-12 月 17 日_

重大變更已對 Microsoft Lync Server 2013 監視基礎結構，開頭的監控伺服器角色已被取代的事實。 監視服務現在已組合在各前端伺服器上，不再是個別的監控伺服器角色 (通常需要組織設定專用電腦來作為監控伺服器)。 此變更的優點之一，就是有助於：

  - 減少實作 Lync Server 2013 時所需的伺服器角色的數量。 在此情況下，減少監控伺服器的伺服器角色也有助於減少成本，因為不需要維護用來監視的專用伺服器。

  - 減少 Lync Server 的安裝和管理的複雜度。 因為監視服務會自動組合在各前端伺服器上，所以您不再需要安裝、設定及管理監控伺服器角色。

<div>


> [!NOTE]  
> 封存伺服器角色也在 Lync Server 2013 中已過時。 監視的服務，例如 Lync Server 2013 封存服務現在組合在每一部前端伺服器上。 這很值得注意，因為監視和封存經常共用相同的 SQL Server 資料庫執行個體。



</div>

如您所預期，這些變更影響主要如何安裝及管理監視服務。 例如，因為監控伺服器角色不存在，監控伺服器] 節點已從 Lync Server 拓撲產生器];接著，這表示您無法再使用拓撲產生器的新監控伺服器] 精靈以監控伺服器新增至您的拓撲。 （不存在該精靈 」。）相反地，您將通常實作監視服務在您的拓撲，請完成下列兩個步驟：

1.  您啟用監視同時設定新的 Lync 伺服器集區。 （在 Lync Server 2013 中，監控會啟用或停用的集區的集區為基礎。）請注意，您可以啟用監視實際收集監視資料，而集區處理程序所述設定 Call Detail Recording and Quality of Experience Settings] 區段中的這份文件。

2.  將監控存放區 (也就是監控資料庫) 與新集區建立關聯。請注意，單一監控存放區可與多個集區建立關聯。依據安置在登錄器集區的使用者數目，這表示您不需要為每個集區設定個別的監控資料庫。單一監控存放區即可供多集區使用。

雖然在您建立新集區的同時啟用監視通常會比較容易，但也可能會建立停用監視的新集區。如果您這麼做，可以在稍後使用拓撲產生器來啟用服務：拓撲產生器有提供一種方法，可為集區啟用或停用監視，或是將集區與不同的監控存放區建立關聯。請記得，雖然已經沒有監控伺服器角色了，您還是需要建立一或多個監控存放區：用來儲存監視服務所收集之資料的後端資料庫。這些後端資料庫可以用 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012 來建立。

<div>


> [!NOTE]  
> 如果集區已啟用 [監控您可以停用的收集監視資料，而不需要變更您的拓樸程序： Lync Server 管理命令介面提供方法，讓您停用 （和稍後重新啟用） 的詳細通話記錄 (CDR) 或品質經驗 (QoE) 資料收集。 如需詳細資訊，請參閱本文件中的＜設定詳細通話記錄和經驗品質設定＞一節。



</div>

一個其他重要的增強功能監視 Lync Server 2013 中為 Lync Server 監視報告現在支援 IPv6 的事實： 使用 [IP 位址] 欄位的報告將顯示 IPv4 或 IPv6 位址根據： 1) 使用; 的 SQL 查詢和，2），或不 IPv6 地址會儲存在監控資料庫中。

<div>


> [!NOTE]  
> 確定 SQL Server Agent 服務的啟動類型是自動，且 [SQL Server Agent 服務執行這保留了監控資料庫之 SQL 執行個體，使預設監控 SQL Server 維護工作可執行其排程的方式控制下的 [SQL Server Agent 服務。



</div>

這份文件引導您逐步完成的安裝和設定 Lync Server 2013 的監視和監控報告程序。 文件中提供逐步指示，將可協助您：

  - 在拓撲中啟用監視，以及將監控存放區與前端集區建立關聯。

  - 安裝 SQL Server Reporting Services 和 Lync 伺服器監視報告。 監視報告是預先設定的報告，針對儲存在監控資料庫中資訊提供不同的觀點。

  - 設定詳細通話記錄 (CDR) 和經驗品質 (QoE) 資料收集。 詳細通話記錄可讓您追蹤使用情況的 Lync Server 功能例如 Voice over IP (VoIP) 通話;立即訊息 (IM);檔案傳輸。音訊/視訊 (A / V) 會議;和應用程式共用工作階段。 QoE 計量追蹤在組織中建立的音訊和視訊通話品質，包括遺失的網路封包數量、背景雜訊和「抖動」(封包延遲差異) 量。

  - 從監控資料庫手動清除 CDR 及/或 QoE 記錄。

</div>

<span> </span>

</div>

</div>

</div>

