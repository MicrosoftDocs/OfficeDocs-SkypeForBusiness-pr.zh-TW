---
title: Lync Server 2013：集中式記錄服務的簡介
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Centralized Logging Service
ms:assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688145(v=OCS.15)
ms:contentKeyID: 49733746
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 647e6b1e5797b3936dc1fef6023c85ce4baf68b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-centralized-logging-service-in-lync-server-2013"></a>Lync Server 2013 中的集中式記錄服務概覽

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

集中式記錄服務的設計目的是為了提供受控制的資料收集方式，以及廣泛或窄的範圍。 您可以同時從部署中的所有伺服器收集資料、定義要追蹤的特定元素、設定追蹤標記，以及從單一電腦或從所有伺服器的所有資料匯總中傳回搜尋結果。 集中式記錄服務會在您部署中的所有伺服器上執行。 集中式記錄服務的架構由下列代理程式和服務所組成：

  - *集中式記錄服務代理程式*   ClsAgent 是與控制器進行通訊的服務可執行檔，並會接收由管理員發出的命令。 此代理程式是在每個 Lync Server 電腦上以服務的方式執行。 當代理程式收到命令時，會執行命令、將訊息傳送給已定義的追蹤元件，然後將追蹤記錄寫入磁片。 它也會讀取其電腦的追蹤記錄，並在要求時將追蹤資料傳送回控制器。 ClsAgent 會偵聽下列埠上的命令： **tcp 50001**、 **Tcp 50002**和**TCP 50003**。

  - *集中式記錄服務控制器*   ClsControllerLib 是 Lync Server 管理命令介面和 ClsController 的命令執行引擎。 CLSControllerLib 會將開始、停止、清除及搜尋命令傳送到 ClsAgent。 傳送搜尋命令時，會將產生的記錄傳回 ClsControllerLib 及匯總。 控制器負責傳送命令至 agent、接收這些命令的狀態，以及管理從搜尋範圍內任何電腦上的所有代理程式傳回的搜尋記錄檔資料，並將記錄資料聚集成有意義且已排序輸出設定。 下列主題中的資訊主要是使用 Lync Server 管理命令介面。 ClsController 受限於 Lync Server 管理命令介面中提供的功能和功能子集。 您可以在命令列中輸入 ClsController 的說明，方法是`ClsController`在 [預設目錄 C：\\Program files\\] 中\\輸入「Microsoft Lync\\Server 2013 ClsAgent」。

**ClsController 通訊至 ClsAgent**

![CLSController 和 CLSAgent 之間的關聯。](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "CLSController 和 CLSAgent 之間的關聯。")

您使用 Windows Server 命令列介面或使用 Lync Server Management Shell 發出命令。 這些命令會在您登入的電腦上執行，並傳送到您部署中的 ClsAgent 本機或其他電腦和池。

ClsAgent 會維護全部的索引檔案。在本機電腦上的快取檔案。 ClsAgent 會將它們分攤80，讓它們均勻分佈于選項 CacheFileLocalFolders 所定義的各個卷上（也就是，本機快取位置和百分比可使用**Set-CsClsConfiguration** Cmdlet 來設定）。 ClsAgent 也負責從本機電腦中老化舊的快取事件追蹤記錄（.etl）檔案。 兩周之後（也就是使用**CsClsConfiguration Cmdlet 設定**的時間範圍），這些檔案會複製到檔案共用，並從本機電腦刪除。 如需詳細資訊，請參閱[設定 CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration)。 當您收到搜尋要求時，會使用搜尋準則來選取一組快取的 .etl 檔案，以根據代理所維護之索引中的值來執行搜尋。

<div>


> [!NOTE]  
> 從本機電腦移至檔案共用的檔案，可以透過 ClsAgent 進行搜尋。 ClsAgent 將檔案移到檔案共用後，ClsAgent 不會維護檔案的老化與移除。 您應該定義系統管理工作來監視檔案共用中的檔案大小，然後刪除檔案或封存檔案。



</div>

所產生的記錄檔案可以使用各種不同的工具來讀取和分析，包括**Snooper**和任何可讀取文字檔（例如**notepad.exe**）的工具。 Snooper 是 Lync Server 2013 調試工具的一部分，可從[http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)下載網頁。

就像 OCSLogger，集中式記錄服務會有數個要追蹤的元件，並提供選取旗標（例如\_tf 元件和\_tf）的選項。 集中式記錄服務也會保留 OCSLogger 的記錄層級選項。

在命令列 ClsController 上使用 Lync Server 管理命令介面最重要的優點是，您可以使用選取的提供者來設定及定義新案例，這些提供者是針對問題空間、自訂標記和記錄層級。 提供給 ClsController 的案例僅限於針對可執行檔所定義的情況。

在舊版中，提供了 OCSLogger，讓系統管理員和支援人員從部署中的電腦收集追蹤檔案。 OCSLogger （針對其所有優點）有一個不足之處。 您在指定時間只能在一部電腦上收集記錄。 您可以使用個別的 OCSLogger 複本登入多部電腦，但最終會有多個記錄，而且沒有簡單的方法來匯總結果。

當使用者要求記錄搜尋時，ClsController 會決定要傳送要求的電腦（亦即根據選取的案例）。 它也會判斷是否需要將搜尋傳送到已儲存的 .etl 檔案所在的檔案共用位置。 當搜尋結果傳回 ClsController 時，控制器會將結果合併成單一時間排序的結果集，並顯示給使用者。 使用者可以將搜尋結果儲存至本機電腦，以進行進一步分析。

當您開機記錄會話時，您會指定與您嘗試解決之問題相關的案例。 您可以隨時執行兩種情況。 這兩種案例的其中一個就是 AlwaysOn 案例。 顧名思義，它應該一直在您的部署中執行，收集所有電腦、池及元件的資訊。

<div>


> [!IMPORTANT]  
> 根據預設，AlwaysOn 情況未在您的部署中執行。 您必須明確啟動案例。 一旦開始，就會繼續執行，直到明確停止為止，且執行狀態將會在電腦重新開機後持續。 如需開始與停止案例的詳細資料，請參閱<A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">使用集中式記錄服務在 Lync server 2013 中捕獲記錄</A>，並在<A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">lync Server 2013 中使用 [停止] 作為集中式記錄服務</A>。



</div>

發生問題時，請先開始與所報告問題相關的第二個案例。 再現問題，並停止記錄第二個案例。 相對於報告的問題開始進行記錄搜尋。 記錄的匯總集合會產生一個記錄檔案，其中包含您網站中所有電腦的追蹤訊息，或部署的全域範圍。 如果搜尋傳回的資料超過您可以 feasibly 分析的資料（通常稱為 [信噪比]，而雜訊太高），您可以執行另一個含有較窄參數的搜尋。 此時，您可以開始注意顯示的模式，並可協助您更清楚地瞭解問題。 最後，在您執行幾個精緻式搜尋之後，您可以找到與問題相關的資料，並找出根本原因。

<div>


> [!TIP]  
> 當您在 Lync Server 中出現問題案例時，請先詢問自己「我已經知道問題為何？」。 如果您要量化問題界限，您可以在 Lync Server 中消除大部分的運營實體部分。<BR>考慮在尋找連絡人時，使用者無法取得目前結果的範例案例。 在媒體元件、企業語音、會議和許多其他元件中，沒有任何問題。 您可能不知道問題的實際原因：在用戶端上，或是伺服器端問題？ 連絡人是由使用者複製程式從 Active Directory 收集，並透過通訊錄服務器（ABServer）傳送至用戶端。 ABServer 會從 RTC 資料庫取得它的更新（使用者複製程式寫入這些檔案），並將它們收集到通訊錄檔案（依預設值為 1:30 AM）。 Lync Server 用戶端會根據隨機排程來取得新的通訊錄。 因為您知道程式的運作方式，所以您可以減少搜尋問題，因為使用者複製程式已從 Active Directory 收集資料，而 ABServer 無法檢索及建立通訊錄檔案，或用戶端無法下載通訊錄檔案。



</div>

</div>

<span> </span>

</div>

</div>

</div>

