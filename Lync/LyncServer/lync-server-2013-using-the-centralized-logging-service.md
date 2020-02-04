---
title: Lync Server 2013：使用集中式記錄服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Centralized Logging Service
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49733700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fb3687d036f7d72160c8af0e168a40d09c84e4b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a>在 Lync Server 2013 中使用集中式記錄服務

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

[集中式記錄服務] 是 Lync Server 2013 的新功能。 它是先前版本中提供的**OCSLogger**和**OCSTracer**工具的增強式取代。 您可以使用集中式記錄服務來執行下列工作：

  - 從單一位置和命令在一或多部電腦和池上開始記錄。

  - 從單一位置和命令停止記錄一或多台電腦和池。

  - 在一或多台電腦和池上搜尋記錄，以尋找單一位置和命令。 您可以調整 search 命令，以傳回已捕獲並儲存在所有電腦上的整個記錄匯總，或傳回可捕獲特定資料的修整結果。

  - 設定記錄會話的方式如下：
    
      - 定義**案例**，或使用預設情況。 集中式記錄服務中的*案例*是由範圍（全域或網站）、案例名稱來識別案例的用途及一或多個提供者所組成。 您可以在任何指定時間在電腦上執行兩種案例。
    
      - 使用現有的*提供者*或建立新的提供者。 *提供者*定義記錄會話收集的內容、詳細資料層級、要追蹤哪些元件，以及要套用哪些旗標。
        
        <div>
        

        > [!TIP]  
        > 如果您熟悉 OCSLogger，則「詞彙<EM>提供者</EM>」會參照<STRONG>元件</STRONG>集合（例如，S4、SIPStack）、<STRONG>記錄類型</STRONG>（例如，WPP、EventLog 或 IIS logfile）、<STRONG>追蹤等級</STRONG>（例如，All、verbose、debug）及<STRONG>旗標</STRONG>（例如 TF_COMPONENT、TF_DIAG）。 這些專案是在提供者（Windows PowerShell 變數）中定義，並傳遞到集中式記錄服務命令。

        
        </div>
    
      - 設定您要從中收集記錄的電腦和池。
    
      - 從 [選項]**網站**中定義記錄會話的範圍（僅限在該網站的電腦上執行記錄捕獲），或 [**全域**] （在部署中的所有電腦上執行記錄捕獲）。

集中式記錄服務功能極其強大，而且幾乎能滿足所有疑難排解問題的需求（大或小）。 從根本原因分析到效能問題，集中式記錄服務可能是任何系統管理員的重要工具。 所有範例都是使用 Lync Server 管理命令介面來顯示。 集中式記錄服務有一個名為**CLSController**的命令列元件。 透過工具本身的命令列工具提供說明。 不過，您可以從命令列執行一組有限的函數。 透過使用 Lync Server 管理命令介面，您可以存取更大且更具可設定的功能。 使用集中式記錄服務時，您必須先將 Lync Server 管理命令介面視為第一個和最重要的方法。

本節中的主題說明如何使用集中式記錄服務，以及如何使用其多種功能的範例。

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 中的集中式記錄服務概覽](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [在 Lync Server 2013 中管理集中式記錄服務設定設定](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [瞭解 Lync Server 2013 中的集中式記錄服務配置設定](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [在 Lync Server 2013 中使用 [開始使用集中式記錄服務] 來捕獲記錄](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [在 Lync Server 2013 中針對集中式記錄服務使用停止功能](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [在 Lync Server 2013 中使用集中式記錄服務所建立的捕獲記錄來進行搜尋](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [從 Lync Server 2013 中的集中式記錄服務讀取捕獲記錄](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

