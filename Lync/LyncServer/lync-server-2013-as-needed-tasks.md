---
title: Lync Server 2013：視需要工作
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 344512a1dd4db44b8290efdcc726275b4a6898de
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a>Lync Server 2013 中的必要工作

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-08-18_

視需要執行下列工作。 標準程式通常也會涵蓋它們：

  - **完整的安全性審核   **您可以定期執行此審核，以回應郵件系統的升級或重新設計，或是回應企圖的（或成功）安全性破壞。 程式可能會涉及伺服器和防火牆上的埠掃描、安全性修正程式的審核，以及協力廠商的滲透測試。

  - **[取代到期**   的憑證] 來檢查 Lync Server 憑證是一般的每週工作，而且是作為系統管理員應記錄所有憑證到期日期的程式。 此記錄可讓系統管理員在特定憑證即將到期並視需要更換時，建立通知。

  - **更新效能基線**   在升級或設定變更後更新效能基線。 貴組織可以使用比較基準來測量效能變更，並偵測出會影響系統效能的問題。

  - **管理**   企業版池初始配置企業版池、標準版伺服器以及貴組織環境中的任何其他伺服器都是在部署個別伺服器期間完成。 針對標準版伺服器與企業版池的伺服器和池進行部署後的管理，包括下列任務：
    
      - 管理前端伺服器
    
      - 管理網路會議
    
      - 管理會議
    
      - 變更服務帳戶認證
    
      - 管理資料庫
    
      - 啟動和停止服務及停用伺服器角色
    
      - 移除伺服器和伺服器角色、移除池，以及解除伺服器和池的授權

  - **管理使用量**   您可以設定 Lync Server 2013，以提供最適合您組織的功能和功能。 這包括下列各項：
    
      - 管理內部部署的網路會議會議支援
    
      - 管理通訊群組的使用來傳送立即訊息
    
      - 管理連絡人、目前狀態和查詢
    
      - 設定用戶端版本篩選
    
      - 設定智慧 IM 篩選
    
      - 設定封存、通話詳細資料錄製，以及符合會議規範

  - **管理邊緣伺服器**   連線日常管理需要提供外部連線的伺服器和設定包括下列各項：
    
      - 管理內部伺服器與邊緣伺服器之間的連線性
    
      - 為邊緣伺服器設定內部與外部介面與憑證
    
      - 管理聯盟夥伴存取

  - **管理通訊錄**   管理通訊錄服務器包括下列各項：
    
      - 設定通訊錄服務器電話正常化
    
      - 從命令列管理通訊錄服務器

  - **管理**   使用者帳戶的使用者帳戶管理包括下列各項：
    
      - 啟用 Lync Server 的使用者帳戶
    
      - 使用嚮導來設定 Lync Server 使用者
    
      - 配置個別的 Lync Server 使用者帳戶屬性
    
      - 搜尋 Lync Server 使用者
    
      - 移動 Lync Server 使用者
    
      - 刪除 Lync Server 使用者

  - **分析 Lync server 2013 記錄**   檔一個非常實用的工具（通常用於疑難排解）是在[使用 lync server 2013 記錄工具](http://technet.microsoft.com/en-us/library/gg558599.aspx)中詳細說明的 lync server 2013 記錄工具。

由於記錄工具會產生記錄檔（在每個伺服器的基礎上），如果電腦上已安裝 Microsoft Office Server 12 資源套件工具，就可以使用 Snooper 工具來查看並分析這些記錄檔。 否則，您也可以使用文字編輯器來分析記錄，這比使用 Snooper 實用程式更不透明且更複雜。

若要查看及分析通訊協定訊息

在記錄工具中，當您結束調試會話時，請按一下 [分析記錄檔]，透過使用 Snooper 工具來查看記錄檔。 您可以分析通訊協定記錄，以取得下列元件：

  - Lync Server SipStack （SIP）

  - Lync Server S4 （SIP）

  - Lync Server 會議信號流量（C3P），包括 MCU 基礎 C3P 和焦點 C3P

  - Lync Server Web 會議流量（PSOM）

  - Lync Server 整合通訊用戶端平臺用戶端（UCCP）

  - 來自存檔資料庫的錯誤報表

若要協助組織所需任務的效能，請參閱視需要作業檢查清單。

<div>


> [!IMPORTANT]  
> 如需詳細的管理與管理程式，請參閱 Microsoft Lync Server 2013 管理指南。



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a>備份（及還原）原則或配置設定

Lync Server 2013 可讓您備份及還原整個系統。 您想要備份的 Iif （可能是天還原）單一原則或單一的配置設定集合、檢索適當的原則，然後將該物件輸送至 Export Clixml Cmdlet，這會將原則資訊儲存為 XML 檔：

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

您現在可以嘗試 RedmondClientPolicy 並變更許多設定。 如果您決定要還原舊原則，請輸入：

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

請注意，這個方法適用于大部分的原則和設定，但它不會搭配一些較複雜的專案（例如包含多個不同語音路由的路由設定設定）來運作。

</div>

</div>

<span> </span>

</div>

</div>

</div>

