---
title: Lync Server 2013： 視工作
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
ms.openlocfilehash: 03a819fad54bbd19be842f7ae28f655186135b50
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a>視需要在 Lync Server 2013 中的工作

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-08-18_

執行下列工作，為必要。 它們通常已涵蓋在標準程序：

  - **完整安全性稽核   **定期，以回應升級或重新設計的郵件系統，或嘗試 （或成功） 的安全性資料外洩回應，您可以執行這項稽核。 程序可能包括伺服器和防火牆、 稽核安全性修正程式上的連接埠掃描，以及協力程式侵入測試。

  - **關於取代憑證到期至**   檢查 Lync 伺服器憑證是其中一個規則的每週工作，且程序的系統管理員應該有一筆記錄的所有憑證的到期日期。 此記錄可讓系統管理員建立通知，當特定憑證即將過期並取代視。

  - **更新效能基準**   更新效能基準在升級或組態變更之後。 您的組織可以使用基準線來測量效能變更，以及偵測會影響系統效能的問題。

  - **管理企業資料庫**   Enterprise 集區、 Standard Edition server 和貴組織的環境中的任何其他伺服器的初始設定已完成的個別伺服器的部署期間。 部署後管理伺服器和 Standard Edition server 的集區和 Enterprise 集區包括下列工作：
    
      - 管理前端伺服器
    
      - 管理 Web 會議
    
      - 管理會議
    
      - 變更服務帳戶認證
    
      - 管理資料庫
    
      - 啟動和停止服務，以及停用伺服器角色
    
      - 移除伺服器及伺服器角色、 移除集區]，和解除委任伺服器和集區

  - **管理流量**   您可以設定 Lync Server 2013 提供最適合貴組織的功能。 其中包括下列項目：
    
      - 管理內部部署 Web 會議會議的支援
    
      - 管理通訊群組，以傳送立即訊息使用
    
      - 管理連絡人、 目前狀態，以及查詢
    
      - 設定用戶端版本篩選
    
      - 設定智慧型 IM 篩選
    
      - 設定封存，請呼叫錄製，以及符合規範的詳細資料

  - **管理 Edge 伺服器連線**   持續管理伺服器和提供外部連線所需的設定包括下列：
    
      - 管理內部伺服器和 Edge Server 之間的連線
    
      - 設定 Edge Server 的內部和外部介面及憑證
    
      - 管理同盟協力廠商存取

  - **管理通訊錄**   管理 Address Book 伺服器包括下列：
    
      - 設定 Address Book Server 電話正規化
    
      - 從命令列管理 Address Book Server

  - **管理使用者帳戶**   管理使用者帳戶包含下列：
    
      - Lync Server 啟用使用者帳戶
    
      - 使用精靈設定 Lync Server 使用者
    
      - 設定個別的 Lync Server 使用者帳戶內容
    
      - Lync Server 使用者搜尋
    
      - 移動 Lync Server 使用者
    
      - 刪除 Lync Server 使用者

  - **分析 Lync Server 2013 記錄檔**   一種非常有用的工具，通常用於疑難排解的方式，是[使用 Lync Server 2013 記錄工具](https://technet.microsoft.com/library/gg558599.aspx)的詳細說明 Lync Server 2013 記錄工具。

因為記錄工具會產生記錄檔 （根據每個伺服器），可以檢視這些記錄檔，且分析使用 Snooper 工具，如果電腦上安裝 Microsoft Office Server 12 Resource Kit 工具。 否則，記錄檔也可以使用文字編輯器，也就是遠低於透明、 更複雜比使用 Snooper 公用程式進行分析。

若要檢視並分析通訊協定的郵件

在 [記錄] 工具中，當您結束偵錯工作階段，按一下 [分析記錄檔，以使用 Snooper 工具檢視記錄檔。 您可以分析通訊協定記錄中的下列元件：

  - Lync Server 裡包含 SipStack (SIP)

  - Lync Server S4 (SIP)

  - Lync Server 會議訊號流量 (C3P)，包括基礎 MCU C3P 和焦點 C3P

  - Lync Server Web 會議流量 (PSOM)

  - Lync Server 整合通訊用戶端平台用戶端 (UCCP)

  - 從封存資料庫的錯誤報告

若要協助您組織所需的工作的效能，請參閱 As-Needed Operations Checklist。

<div>


> [!IMPORTANT]  
> 如需詳細的系統管理與管理程序，請參閱 < Microsoft Lync Server 2013 系統管理指南。



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a>備份 （與還原） 的原則或組態設定

Lync Server 2013 可讓您備份及還原整個系統。 Iif 您想要備份伺服器陣列 （，然後也許有一天還原） 的單一原則或組態設定的單一集合擷取適當的原則，並再將以管線傳輸至 Export-clixml 指令程式，將原則資訊儲存為 XML 檔案的物件：

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

您現在可能試驗 RedmondClientPolicy，並變更大量的設定。 如果您改為決定要還原舊的原則，請輸入：

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

請注意，此方法適用於大部分的原則和設定，但它不會使用一些更複雜的項目-包含多個的子物件 （例如路由組態設定，其中包含許多不同的語音路由） 的項目。

</div>

</div>

<span> </span>

</div>

</div>

</div>

