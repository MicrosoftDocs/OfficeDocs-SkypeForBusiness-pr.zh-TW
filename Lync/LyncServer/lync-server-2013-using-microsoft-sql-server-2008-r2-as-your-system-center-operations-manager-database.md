---
title: Lync Server 2013：使用 Microsoft SQL Server 2008 R2 作為 System Center Operations Manager 資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49733555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51dbff3748f342bd630c33fc867a4249b386c00c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518820"
---
# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a>使用 Microsoft SQL Server 2008 R2 作為 Lync Server 2013 的 System Center Operations Manager 資料庫

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-29_

若要使用 SQL Server 2008 R2 作為後端資料庫，請完成本主題所述的步驟。

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a>設定 SQL Server 2008 R2 和 SQL Server Reporting Services

開始安裝 System Center Operations Manager 之前，您必須對 SQL Server 2008 R2 和 SQL Server Reporting Services 設定進行兩項變更。  (只有當您使用 SQL Server 2008 R2 作為 Operations Manager 資料庫時，才需要這些變更。 ) 首先，在將會裝載 Operations Manager 資料庫的電腦上執行下列動作：

1.  按一下 [開始]****，然後按 [執行]****。

2.  在 [ **執行** ] 對話方塊中，輸入 **C： \\ Program Files \\ Microsoft SQL Server \\ MSRS10 \_ 而 archinst \\ Reporting Services \\ ReportServer** 然後按 enter。

3.  在 **ReportServer** 資料夾中，以 [記事本] 或任何其他文字編輯器來開啟 **rsreportserver.config** 檔案。

4.  您會在靠近檔案開頭的地方，看到一連串的 "Add Key" 節點。 尋找開始** \< Add Key = "SecureConnectionLevel"** 的專案，並將值設為**0**：
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  儲存 **rsreportserver.config** 檔案，然後關閉文字編輯器。

更新報告伺服器組態檔之後，您必須指派正確的憑證給 SQL Server Reporting Services。若要執行這項作業，請完成下列程序：

1.  依序按一下 [ **開始**]、[ **所有程式**]、 **[Microsoft SQL Server 2008 R2**] 及 [設定 **工具**]，然後按一下 [ **Reporting Services 設定管理員**]。

2.  在 [Reporting Services 組態連接]**** 對話方塊中，確定您的伺服器名稱出現在 [伺服器名稱]**** 方塊中。 選取將主控 Operations Manager 資料庫的 SQL Server 實例 (例如，從 [**報表伺服器實例**] 下拉式清單中) **而 archinst** ，然後按一下 **[連接]**。

3.  在 Reporting Services 組態管理員中，按一下 [Web 服務 URL]****。

4.  在「Web 服務 URL」**** 頁面上，從 [SSL 憑證]**** 下拉式清單中選取要用於 Reporting Services 的憑證，然後按一下 [套用]****。幾秒鐘之後，您就會看到 [報告伺服器 Web 服務 URL]**** 底下列出一對 URL。

5.  在兩個 URL 上都按一下，以確認您可以存取 SQL Server Reporting Services。

6.  關閉 Reporting Services 組態管理員。

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a>建立 System Center Operations Manager 資料庫以搭配 SQL Server 2008 R2 使用

如果您想要將 System Center Operations Manager 設定為使用 SQL Server 2008 R2 資料庫，您必須在執行 SQL Server 2008 R2 的電腦上「手動」建立 Operations Manager 資料庫。  (此外，如果您使用 SQL Server 2005 或 SQL Server 2008 作為後端資料庫，則不需要這些步驟。 ) 

若要手動建立 Operations Manager 資料庫，請執行下列動作：

1.  在 System Center Operations Manager 2007 R2 安裝媒體上，按兩下 [SupportTools \\ AMD64] 資料夾中的 [ **DBCreateWizard.exe**]。

2.  在 [資料庫設定精靈] 的「歡迎使用資料庫設定精靈」**** 頁面上，按 [下一步]****。

3.  在「資料庫資訊」**** 頁面上，將所有設定保留原狀，然後按 [下一步]****。

4.  在 [**管理群組**設定] 頁面上，輸入管理群組的名稱 (例如，[**管理組名**] 方塊中的 [ **Lync Server Monitoring**) ]，然後按 **[下一步]**。

5.  在「Operations Manager 錯誤報告」**** 頁面上，按 [下一步]****。

6.  在「摘要」**** 頁面上，按一下 [完成]****。

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a>建立 System Center Operations Manager 資料倉儲以搭配 SQL Server 2008 R2 使用

Microsoft Lync Server 2013 隨附三個新的 System Center Operations Manager 報告：

  - **端對端案例可用性報告**    此報表詳述主要 Lync Server 服務（如註冊或目前狀態）的可用性/運作時間。

  - **容量報告**    此報告使用效能計數器資訊，顯示系統元件的趨勢，例如記憶體可用性及處理器使用量。

  - **元件報告**    這份報告會列出排名依 Lync Server 元件分組的上方警示發生器。

為了使用這些新報告，您必須安裝 System Center Operations Manager 資料倉儲。  (資料倉儲可用於長期儲存作業資料。 ) 若要使用具有 SQL Server 2008 R2 的資料倉儲，您必須在主控 SQL Server 資料庫的電腦上執行下列步驟：

1.  在 System Center Operations Manager 安裝程式媒體上，按兩下 [安裝 SupportTools AMD64] 資料夾中的 [ \\ \\ **DBCreateWizard.exe**]。

2.  在 [資料庫設定精靈] 的「歡迎使用資料庫設定精靈」**** 頁面上，按 [下一步]****。

3.  在「資料庫資訊」**** 頁面上，從 [資料庫類型]**** 下拉式清單中選取 [Operations Manager 資料倉儲資料庫]****，然後按 [下一步]****。

4.  在「摘要」**** 頁面上，按一下 [完成]****。

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a>安裝 System Center Operations Manager 主控台

Operations Manager 主控台是用來管理 System Center Operations Manager 的主要工具。 在安裝 Operations Manager 主控台之前，請確定您已安裝支援的 SQL Server 版本和 SQL Server 報表服務。 此外，也建議您執行 SQL Server 的 Reporting Services 組態管理員，以確認 Reporting Service 已正確安裝及設定。

若要安裝 System Center Operations Manager 主控台：

1.  在 System Center Operations Manager 安裝媒體上，按兩下 [ **SetupOM.exe**]。

2.  在 System Center Operations Manager 2007 R2 安裝程式中，按一下 [ **檢查必要條件**]。

3.  在 System Center Operations Manager 先決條件檢視器中，選取要安裝的 System Center 元件： (**Server**; **主控台**;然後 **PowerShell**) ，然後按一下 [ **檢查**]。 確認沒有報告任何封鎖問題，然後按一下 [關閉]****。 如果有報告封鎖問題，請更正問題，然後按一下 [檢查]****，重新執行必要條件測試。

4.  在 System Center Operations Manager 安裝程式中，按一下 [ **安裝 Operations Manager**]。

5.  在 System Center Operations Manager 安裝精靈的 [ **歡迎使用 System Center Operations Manager 安裝程式]** 頁面上，按 **[下一步]**。

6.  在「使用者授權合約」**** 頁面上，選取 [我接受授權合約中的條款]****，然後按 [下一步]****。

7.  在「產品註冊」**** 頁面上的 [使用者名稱]**** 方塊中，輸入您的名稱，並且在 [組織]**** 方塊中輸入組織的名稱。 在 [ **輸入25位數的 CD 金鑰** ] 方塊中，輸入您的 System Center Operations Manager 產品金鑰，然後按 **[下一步]**。

8.  在「自訂安裝程式」**** 頁面上，選取所要安裝的 System Center 選項，然後按 [下一步]****。您應選取 [管理伺服器]****、[資料庫使用者介面]**** 及 [Web 主控台]**** 以進行安裝。不應選取 [資料庫]****，也不應安裝。

9.  在 [ **SC Database Server Instance** ] 頁面上，確認安裝 Operations Manager 資料庫之電腦的名稱出現在 [ **System Center 資料庫伺服器** ] 方塊中。 按 [下一步]****。

10. 在「管理伺服器動作帳戶」**** 頁面上，選取 [網域或本機電腦帳戶]****，然後在 [使用者帳戶]****、[密碼]**** 及 [網域或本機電腦]**** 方塊中輸入適當的值。按 [下一步]****。

11. 在「SDK 和設定服務帳戶」**** 頁面上，選取 [網域或本機電腦帳戶]****，然後在 [使用者帳戶]****、[密碼]**** 及 [網域或本機電腦]**** 方塊中輸入適當的值。按 [下一步]****。

12. 在「Operations Manager 錯誤報告」**** 頁面上，按 [下一步]****。

13. 在「客戶經驗改進計畫」**** 頁面上，按 [下一步]****。

14. 在「已完成安裝程式的準備工作」**** 頁面上，按一下 [安裝]****。

15. 在「正在完成 System Center Operations Manager 安裝程式」**** 頁面上，清除 [備份加密金鑰]**** 及 [啟動主控台]**** 核取方塊，然後按一下 [完成]****。

16. 在 System Center Operations Manager 安裝程式 **中，按一下**[結束]。

</div>

<div>

## <a name="installing-system-center-reporting-services"></a>安裝 System Center Reporting Services

安裝及設定 System Center Operations Manager 主控台之後，您必須先安裝 System Center Reporting Services。 如果您使用 SQL Server 2008 R2 作為 Operations Manager 後端資料庫，這表示您必須先對與 SQL Server Reporting Services 相關聯的安全性群組進行暫時的變更。 如果您使用的是 SQL Server 2008 R2，您必須執行下列作業：

1.  按一下 [開始]****，指向 [系統管理工具]****，然後按一下 [伺服器管理員]****。

2.  在伺服器管理員中，依序展開 [設定]**** 及 [本機使用者和群組]****，然後按一下 [群組]****。

3.  找到下列群組，其中 atl-ws-01-001 代表您電腦的名稱，而而 ARCHINST 代表 System Center 資料庫的 SQL Server 實例： **SQLServerReportServerUser $ atl-ws-01-001 $ MSRS10 \_ 50. 而 archinst**。

4.  以滑鼠右鍵按一下該群組，然後按一下 [重新命名]****。 從群組名稱中刪除** \_ 50** ，以重新命名群組。 例如： **SQLServerReportServerUser $ atl-ws-01-001-001 $ MSRS10。而 ARCHINST**。

5.  關閉伺服器管理員。

這時候，您已經準備好可以安裝 System Center Reporting Services。若要執行這項作業，請完成下列程序：

1.  在 System Center Operations Manager 2007 R2 安裝媒體上，按兩下 [ **SetupOM.exe**]。

2.  在 System Center Operations Manager 2007 R2 安裝程式中，按一下 [ **安裝 Operations Manager 報告**]。

3.  在 System Center Operations Manager 2007 R2 報表安裝精靈的 [ **歡迎使用 Operations Manager 報告安裝程式** ] 頁面上，按 **[下一步]**。

4.  在「使用者授權合約」**** 頁面上，選取 [我接受授權合約中的條款]****，然後按 [下一步]****。

5.  在「產品註冊」**** 頁面上，確定您的名稱和組織的名稱分別出現在 [使用者名稱]**** 和 [組織]**** 方塊中，然後按 [下一步]****。

6.  在「自訂安裝程式」**** 頁面上，按一下 [報告伺服器]****，並選取 [這個元件以及所有相依的元件會安裝到本機硬碟]****。按一下 [資料倉儲]****，並選取 [這個元件將無法使用]****，然後按 [下一步]****。

7.  在「連線至 Root Management Server」**** 頁面上的 [Root Management Server]**** 方塊中，輸入 Operations Manager Root Management Server 的名稱，然後按 [下一步]****。

8.  在「連線到 Operations Manager 資料倉儲」**** 頁面上的 [SQL Server 執行個體]**** 方塊中，輸入資料倉儲所在的 SQL Server 執行個體。(如果資料倉儲位在預設執行個體中，則直接輸入伺服器名稱即可；例如：atl-sql-001。) 確認資料庫名稱 **OperationsManagerDW** 出現在 [名稱]**** 方塊中，而且連接埠 **1433** 出現在 [SQL Server 連接埠]**** 方塊中。按 [下一步]****。

9.  在「SQL Server 報告執行個體」**** 頁面上，從 [輸入 SQL Server Reporting Services 伺服器]**** 下拉式清單中選取 SQL Server 報告伺服器，然後 [下一步]****。

10. 在「資料倉儲寫入帳戶」**** 頁面上的 [使用者帳戶]**** 和 [密碼]**** 方塊中，輸入一開始要為其指派資料倉儲寫入權限的使用者名稱和密碼。從 [網域]**** 下拉式清單中選取使用者的網域，然後按 [下一步]****。

11. 在「資料讀取器帳戶」**** 頁面上的 [使用者帳戶]**** 和 [密碼]**** 方塊中，輸入當 SQL Reporting Services 查詢資料倉儲時，所要使用之使用者帳戶的名稱和密碼。從 [網域]**** 下拉式清單中選取帳戶網域，然後按 [下一步]****。

12. 在「操作資料報告」**** 頁面上，按 [下一步]****。

13. 在「Microsoft Update」**** 頁面上，按 [下一步]****。

14. 在「已完成安裝程式的準備工作」**** 頁面上，按一下 [安裝]****。

15. 在「正在完成 Operations Manager 報告元件安裝精靈」**** 頁面上，按一下 [完成]****。

16. 在 System Center Operations Manager 2007 R2 安裝程式中 **，按一下 [** 結束]。

安裝 System Center 報表之後，您可以使用下列程式重設與 SQL Server 報表相關聯之安全性群組的名稱。 同樣地，只有在您使用 SQL Server 時，才需要此程式：

1.  按一下 [開始]****，指向 [系統管理工具]****，然後按一下 [伺服器管理員]****。

2.  在伺服器管理員中，依序展開 [設定]**** 及 [本機使用者和群組]****，然後按一下 [群組]****。

3.  找出下列群組，其中 atl-ws-01-001 代表您電腦的名稱，而而 ARCHINST 代表封存與監控資料庫的 SQL Server 實例： **SQLServerReportServerUser $ atl-ws-01-001-001 $ MSRS10。而 ARCHINST**。

4.  以滑鼠右鍵按一下該群組，然後按一下 [重新命名]****。 將** \_ 50**新增至組名的結尾，然後在 SQL Server 實例名稱之前新增，以重新命名群組。 例如： **SQLServerReportServerUser $ atl-ws-01-001-001 $ MSRS10 \_ 50. 而 archinst**。

5.  關閉伺服器管理員。

如果 System Center 操作主控台開啟，則您需要關閉應用程式，然後再重新啟動；如果不這麼做，[報告]**** 索引標籤不會出現在操作主控台使用者介面中。請注意，第一次重新啟動操作主控台之後，可能需要幾分鐘的時間，監視報告才會全部出現在 [報告]**** 索引標籤中。

</div>

</div>

<span> </span>

</div>

</div>

</div>

