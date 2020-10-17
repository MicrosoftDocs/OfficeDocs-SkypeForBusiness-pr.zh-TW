---
title: Lync Server 2013：集中式記錄服務概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Centralized Logging Service
ms:assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688145(v=OCS.15)
ms:contentKeyID: 49733746
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e1c382151d34751e7e934f15fdd2855ce696e06
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520830"
---
# <a name="overview-of-the-centralized-logging-service-in-lync-server-2013"></a>Lync Server 2013 中的集中式記錄服務概述

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

集中式記錄服務的設計目的是要提供一種具有廣泛或窄範圍之資料的可控集合方式。 您可以同時從部署的所有伺服器收集資料、定義要追蹤的特定元素、設定追蹤旗標，以及從單一電腦或所有伺服器的所有資料匯總中傳回搜尋結果。 集中式記錄服務會在您部署中的所有伺服器上執行。 集中式記錄服務的架構是由下列代理程式和服務所組成：

  - *集中式記錄服務代理程式*    ClsAgent.exe 是與控制器通訊的服務可執行檔，並接收由系統管理員發出的控制器命令。 代理程式會在每一部 Lync Server 電腦上以服務的身分執行。 當代理程式收到命令時，它會執行命令、將郵件傳送至已定義的追蹤元件，然後將追蹤記錄檔寫入磁片。 它也會讀取其電腦的追蹤記錄檔，並在要求時將追蹤資料傳送回控制器。 ClsAgent 會偵聽下列埠上的命令： **tcp 50001**、 **Tcp 50002**及 **tcp 50003**。

  - *集中式記錄服務控制器*    ClsControllerLib.dll 是 Lync Server 管理命令介面和 ClsController.exe 的命令執行引擎。 CLSControllerLib.dll 會將開始、停止、清除和搜尋命令傳送給 ClsAgent。 當傳送搜尋命令時，產生的記錄會傳回 ClsControllerLib.dll 並匯總。 控制器負責將命令傳送給代理程式、接收這些命令的狀態，以及在搜尋範圍中的任何電腦上的所有 agent 傳回時，管理搜尋記錄檔資料，並將記錄資料聚合到有意義的已排序輸出集。 下列主題中的資訊重點是使用 Lync Server 管理命令介面。 ClsController.exe 會限制在 Lync Server 管理命令介面中提供的功能和功能的子集。 您可以在命令列上輸入「 `ClsController` \\ \\ \\ Microsoft Lync Server 2013 ClsAgent 中的預設目錄 C： Program files 通用檔案，以取得 ClsController.exe 的協助 \\ 。

**ClsController ClsAgent 的通訊**

![CLSController 和 CLSAgent 之間的關聯性。](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "CLSController 和 CLSAgent 之間的關聯性。")

使用 Windows Server 命令列介面或 Lync Server 管理命令介面發出命令。 命令會在您登入的電腦上執行，並傳送至本機的 ClsAgent，或部署中的其他電腦及集區。

ClsAgent 會維護全部的索引檔案。在本機電腦上的快取檔。 ClsAgent 會將其分配給它們，使其平均分散于選項 CacheFileLocalFolders 所定義的各個磁片區上，每個磁片區絕對使用超過 80% (也就是說，本機快取位置和百分比可使用 **Set-CsClsConfiguration** Cmdlet) 來設定。 ClsAgent 也負責帳齡舊的快取事件追蹤記錄檔 ( .etl) 本機電腦。 在兩周後 (也就是說，可使用 **Set-CsClsConfiguration** Cmdlet 來設定時間範圍) 這些檔案會複製到檔案共用，並從本機電腦刪除。 如需詳細資訊，請參閱 [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration)。 當接收搜尋要求時，搜尋準則是用來選取一組快取的 .etl 檔案，以根據代理程式所維護之索引中的值來執行搜尋。

<div>


> [!NOTE]  
> 從本機電腦移至檔案共用的檔案，可依 ClsAgent 進行搜尋。 一旦 ClsAgent 將檔案移至檔案共用，檔案的老化和移除不會由 ClsAgent 維護。 您應定義管理工作，以監視檔案共用中的檔案大小，並刪除或封存檔案。



</div>

您可以使用各種工具讀取及分析產生的記錄檔，包括 **Snooper.exe** 和任何可讀取文字檔的工具，例如 **Notepad.exe**。 Snooper.exe 是 Lync Server 2013 調試工具的一部分，可從下載網頁 [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257) 。

就像 OCSLogger 一樣，集中式記錄服務也會有多個元件可供追蹤，並提供選擇旗標（如 TF COMPONENT 和 TF options）的選項 \_ \_ 。 集中式記錄服務也會保留 OCSLogger 的記錄等級選項。

在命令列 ClsController 上使用 Lync Server 管理命令介面最重要的優點是，您可以使用選取的提供者來設定及定義新的案例，其是以問題空間、自訂旗標及記錄層級為目標。 可用於 ClsController 的案例只限于為可執行檔定義的案例。

在舊版中，提供 OCSLogger.exe，讓系統管理員和支援人員在部署中從電腦收集追蹤檔案。 OCSLogger，針對其所有優點，都有缺點。 在指定的時間，您只能在一部電腦上收集記錄檔。 您可以使用不同的 OCSLogger 副本登入多部電腦，但是會以多個記錄檔結束，而且不會有簡單的方法來匯總結果。

當使用者要求記錄搜尋時，ClsController 會根據) 所選案例，決定要將要求傳送給 (的機器。 此外，它也會判斷是否需要將搜尋傳送至儲存的 .etl 檔案所在的檔案共用。 當搜尋結果傳回 ClsController 時，控制器會將結果合併為使用者所呈現的單一時序結果集。 使用者可以將搜尋結果儲存至本機機器，以進行進一步分析。

當您開機記錄會話時，您會指定要嘗試解決之問題的相關案例。 您可以隨時執行兩個案例。 這兩種案例之一應該是 AlwaysOn 案例。 顧名思義，它應永遠在您的部署中執行，並收集所有電腦、集區和元件的資訊。

<div>


> [!IMPORTANT]  
> 根據預設，AlwaysOn 案例不會在您的部署中執行。 您必須明確地啟動案例。 一旦開始，它會繼續執行，直到明確停止為止，而且執行狀態會持續重新開機電腦。 如需啟動和停止案例的詳細資訊，請參閱 <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">使用 Start for a 集中式記錄服務來捕獲 Lync server 2013 中的記錄</A> ，並 <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">在 lync Server 2013 中使用「集中式記錄」服務的 Stop</A>。



</div>

發生問題時，請啟動與所報告問題相關的第二個案例。 再現問題，並停止記錄第二個案例。 相對於所報告的問題，開始進行記錄搜尋。 記錄的匯總集合會產生記錄檔，該檔案包含您的網站中所有電腦的追蹤訊息，或部署的全域範圍中的追蹤訊息。 如果搜尋傳回的資料多於您可以 feasibly 分析 (通常稱為雜訊對雜訊比例，在此情況下，噪音太高) ，您可以使用較窄的參數執行另一次搜尋。 此時，您可以開始注意所顯示的模式，並可協助您取得問題的更清晰的重點。 最後，在您執行一些精簡搜尋之後，您可以尋找與問題相關的資料，並找出根本原因。

<div>


> [!TIP]  
> 當您在 Lync Server 中呈現問題案例時，請從提問「我已經知道這個問題的資訊」。 如果您量化問題的界限，您可以在 Lync Server 中消除大部分的運作實體部分。<BR>請考慮一個範例案例，您知道使用者在尋找連絡人時並未取得目前的結果。 沒有任何一點要尋找媒體元件、Enterprise Voice、會議及許多其他元件的問題。 您可能不會知道問題實際上是在用戶端上，還是伺服器端問題？ 使用者收集器會從 Active Directory 收集連絡人，並透過通訊錄服務器 (ABServer) 來傳遞給用戶端。 ABServer 會從 RTC (資料庫中取得更新，以供使用者複寫器寫入其) 並將其收集到通訊錄檔案中（預設為 1:30 AM）。 Lync Server 用戶端會以隨機排程的，取回新的通訊錄。 因為您知道程式的運作方式，所以您可以縮小搜尋，以找出可能導致問題的潛在原因，以供使用者複寫器從 Active Directory 收集的資料，ABServer 不會檢索及建立通訊錄檔案，或用戶端不會下載通訊錄檔案。



</div>

</div>

<span> </span>

</div>

</div>

</div>

