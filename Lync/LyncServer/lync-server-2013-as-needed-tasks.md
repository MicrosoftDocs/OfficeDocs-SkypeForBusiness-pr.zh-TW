---
title: Lync Server 2013：必要任務
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
ms.openlocfilehash: 98b4323374c9801ec07930941a0daa3635b04e43
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529540"
---
# <a name="as-needed-tasks-in-lync-server-2013"></a>Lync Server 2013 中的必要工作

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-08-18_

請視需要執行下列工作。 它們經常也包含在標準程式中：

  - **完整安全性審核   **您可以定期執行此審核，以回應郵件系統的升級或重新設計，或是回應嘗試的 (或成功的) 安全性破壞。 此程式可能會包含伺服器及防火牆上的埠掃描、安全性修正程式的核查，以及協力廠商的滲透測試。

  - **取代憑證，使其到期**    檢查 Lync Server 憑證是一項正常的周任務，也就是管理員應該有所有憑證到期日記錄的步驟。 這筆記錄可讓系統管理員在特定憑證到期時建立通知，並視需要更換。

  - **更新效能基準**    在升級或設定變更之後更新效能基準。 您的組織可以使用基準來測量效能變更，並偵測影響系統效能的問題。

  - **管理企業版集**     區部署個別的伺服器時，已完成組織環境中的 Enterprise pool、Standard Edition 伺服器及其他任何伺服器的初始設定。 Standard Edition server 和 Enterprise pool 的伺服器及集區的部署後管理包括下列工作：
    
      - 管理前端伺服器
    
      - 管理 Web 會議
    
      - 管理會議
    
      - 變更服務帳戶認證
    
      - 管理資料庫
    
      - 啟動和停止服務以及停用伺服器角色
    
      - 移除伺服器和伺服器角色、移除集區，以及解除委任伺服器與集區

  - **管理使用量**    您可以設定 Lync Server 2013，以提供最適合貴組織的功能。 其中包括下列項目：
    
      - 管理內部部署 Web 會議會議的支援
    
      - 管理通訊群組的使用以傳送立即訊息
    
      - 管理連絡人、目前狀態及查詢
    
      - 設定用戶端版本篩選
    
      - 設定智慧 IM 篩選
    
      - 設定封存、詳細通話記錄和會議規範

  - **管理 Edge Server 連線能力**    持續管理提供外部連線所需的伺服器及設定包括下列各項：
    
      - 管理內部伺服器和 Edge Server 之間的連線
    
      - 設定 Edge Server 的內部及外部介面和憑證
    
      - 管理同盟合作夥伴存取

  - **管理通訊錄**    管理通訊錄服務器包含下列專案：
    
      - 設定通訊錄服務器電話正常化
    
      - 從命令列管理通訊錄服務器

  - **管理使用者帳戶**    管理使用者帳戶包括下列專案：
    
      - 啟用 Lync Server 的使用者帳戶
    
      - 使用嚮導設定 Lync Server 使用者
    
      - 設定個別的 Lync Server 使用者帳戶屬性
    
      - 搜尋 Lync Server 使用者
    
      - 移動 Lync Server 使用者
    
      - 刪除 Lync Server 使用者

  - **分析 Lync Server 2013 記錄**     檔一種非常有用的工具（一般用於疑難排解）是「lync Server 2013 記錄」工具，詳細資訊請參閱[使用 Lync server 2013 記錄工具](https://technet.microsoft.com/library/gg558599.aspx)。

因為「記錄」工具會以每個伺服器為基礎來產生記錄檔 () ，如果電腦上已安裝 Microsoft Office Server 12 資源套件工具，則可以使用 Snooper 工具來查看及分析這些記錄檔。 否則，也可以使用文字編輯器來分析記錄檔，此編輯器的透明度不如使用 Snooper 實用程式複雜。

若要查看及分析通訊協定訊息

在記錄工具中，當您結束調試會話時，請按一下 [分析記錄檔] 以使用 Snooper 工具來查看記錄檔。 您可以分析下列元件的通訊協定記錄：

  - Lync Server SipStack (SIP) 

  - Lync Server S4 (SIP) 

  - Lync Server 會議信號流量 (C3P) （包括 MCU 基礎 C3P 和 Focus C3P）

  - Lync Server Web 會議流量 (PSOM) 

  - Lync Server 整合通訊用戶端平臺用戶端 (UCCP) 

  - 封存資料庫的錯誤報表

若要協助組織所需任務的效能，請參閱 As-Needed 作業檢查清單。

<div>


> [!IMPORTANT]  
> 如需詳細的系統管理和管理程式，請參閱 Microsoft Lync Server 2013 管理指南。



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a>備份 (及還原) 原則或配置設定

Lync Server 2013 可讓您備份及還原整個系統。 Iif 您要備份 (，然後可能是天的還原) 單一原則或單一的設定集集合、檢索適當的原則，然後將該物件以管道傳送至 Export-Clixml Cmdlet，該物件會將原則資訊儲存為 XML 檔案：

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

您現在可以試驗 RedmondClientPolicy，並變更許多設定。 如果您決定改為還原舊的原則，請輸入：

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

請注意，此方法適用于大部分的原則及設定，但不會使用某些較複雜的專案（包含多個子物件的專案） (例如路由設定設定，其中包含許多不同的語音路由) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

