---
title: Lync Server 2013： 使用集中式的記錄服務
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
ms.openlocfilehash: 1a5aa8e93bed162219da1ad522483d61b003a603
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a>使用 Lync Server 2013 中的集中式的記錄服務

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

The Centralized Logging Service 是在 Lync Server 2013 中的新功能。 它是舊版 **OCSLogger** 和 **OCSTracer** 工具的增強替代功能。 您可以使用集中式記錄服務若要執行下列工作：

  - 開始從單一位置和命令登入一或多個電腦和集區。

  - 停止從單一位置和命令登入一或多個電腦和集區。

  - 搜尋一或多個電腦和集區上的記錄檔，找出單一位置或命令。您可以量身打造搜尋命令，傳回所有電腦上擷取和儲存的整個記錄檔彙總，或傳回會擷取特定資料的已整理結果。

  - 如下設定記錄工作階段：
    
      - 定義**案例**，或使用預設案例。 Centralized Logging Service 中的*案例*組成範圍 (全域或網站)，來識別此案例中，與一或多個提供者的目的分析藍本名稱。 您可以在任何指定的時間於一部電腦上執行兩個案例。
    
      - 使用現有*提供者*或建立新的提供者。*提供者*定義記錄工作階段所收集的內容、內容的詳細程度、要追蹤哪些元件，以及要套用哪些旗標。
        
        <div>
        

        > [!TIP]  
        > 如果您熟悉 OCSLogger，<EM>提供者</EM>一詞是指<STRONG>元件</STRONG> (例如，S4、SIPStack)、<STRONG>記錄類型</STRONG> (例如，WPP、EventLog 或 IIS logfile)、<STRONG>記錄層次</STRONG> (例如，全部、詳細、偵錯) 及<STRONG>旗標</STRONG> (例如，TF_COMPONENT、TF_DIAG) 的集合。 這些項目會提供者 （Windows PowerShell 變數） 中所定義，並傳遞至 Centralized Logging Service 命令。

        
        </div>
    
      - 設定要從中收集記錄的電腦和集區。
    
      - 從選項**網站** (僅在該網站中的電腦執行記錄擷取) 或**全域** (在部署中所有的電腦上執行記錄擷取) 定義記錄工作階段的範圍。

The Centralized Logging Service 具有強大的功能，而且可以符合幾乎所有的問題的疑難排解需求 — 大型或小型。 從效能問題的根本原因分析，the Centralized Logging Service 可以是任何系統管理員的重要工具。 所有範例會都顯示使用 Lync Server 管理命令介面。 沒有 the Centralized Logging Service 呼叫**CLSController.exe**的命令列元件。 命令列工具本身提供說明。 不過，不過，您只能從命令列執行有限的功能。 使用 Lync Server 管理命令介面，您可以存取一組更大且更可設定的功能。 使用集中式記錄服務時，應一律做為第一個及最重要方法考量 Lync Server 管理命令介面。

本節中的主題說明如何使用集中式記錄服務及如何使用其中眾多功能的範例。

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中的集中式的記錄服務概觀](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [管理 Lync Server 2013 中的集中式記錄服務組態設定](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [了解在 Lync Server 2013 中的集中式記錄服務組態設定](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [將 Start 用於集中式記錄服務以擷取在 Lync Server 2013 中的記錄](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [將 Stop 用於 Lync Server 2013 中的集中式的記錄服務](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [使用集中式記錄服務在 Lync Server 2013 中建立的擷取記錄上的搜尋](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [讀取 the Centralized Logging Service Lync Server 2013 中擷取記錄](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

