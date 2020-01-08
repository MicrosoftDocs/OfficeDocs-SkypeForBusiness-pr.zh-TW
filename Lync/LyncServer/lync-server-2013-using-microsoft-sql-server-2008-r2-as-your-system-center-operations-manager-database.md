---
title: Lync Server 2013：使用 Microsoft SQL Server 2008 R2 作為 System Center Operations Manager 資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49733555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 858134b4d7f2a2fbc4e15c14e121ac12679c9ddc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982701"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a>使用 Microsoft SQL Server 2008 R2 作為 Lync Server 2013 的 System Center Operations Manager 資料庫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-29_

若要使用 SQL Server 2008 R2 作為後端資料庫，請完成本主題中詳細說明的步驟。

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a>正在設定 SQL Server 2008 R2 與 SQL Server Reporting Services

您必須先對 SQL Server 2008 R2 以及 SQL Server Reporting Services 設定進行兩個變更，才能開始安裝 System Center 作業管理器。 （只有當您使用 SQL Server 2008 R2 作為 Operations Manager 資料庫時，才需要進行這些變更。）首先，請在將裝載 Operations Manager 資料庫的電腦上執行下列動作：

1.  按一下 [**開始**]，然後按一下 [**執行**]。

2.  在 [**執行**] 對話方塊中，**輸入 C\\： Program\\Files Microsoft SQL\\ Server\_MSRS10 50.\\ARCHINST Reporting\\Services ReportServer** ，然後按 enter。

3.  在 [ **ReportServer** ] 資料夾中，在 [記事本] 或任何其他文字編輯器中開啟 [檔案**rsreportserver** ]。

4.  在靠近檔案開頭的位置，您會看到一系列的 "Add Key" （新增鍵）節點。 找出開始** \<新增索引鍵 = "SecureConnectionLevel"** 的專案，並將值設為**0**：
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  儲存檔**rsreportserver** ，然後關閉您的文字編輯器。

更新報表伺服器設定檔之後，您必須將正確的憑證指派給 SQL Server Reporting Services。 若要執行此動作：

1.  按一下 [**開始**]，按一下 [**所有程式**]，按一下 **[Microsoft SQL Server 2008 R2**]，按一下 [設定**工具**]，然後按一下 [ **Reporting Services Configuration Manager**]。

2.  在 [ **Reporting Services**設定連線] 對話方塊中，確定您的伺服器名稱出現在 [**伺服器名稱**] 方塊中。 從 [**報表伺服器實例**] 下拉式清單中選取將承載 Operations Manager 資料庫的 SQL Server 實例（例如**ARCHINST**），然後按一下 **[連線]**。

3.  在 Reporting Services 組態管理員中，按一下 [ **Web 服務 URL**]。

4.  在 [ **Web 服務 URL** ] 頁面上，選取要用於 [ **SSL 憑證**] 下拉式清單中的 [報表服務] 的憑證，**然後按一下 [** 套用]。 幾秒鐘之後，您會在 [**報表伺服器 Web 服務 url**] 底下看到一組 url。

5.  按一下兩個 Url，確認您可以存取 SQL Server Reporting Services。

6.  關閉 Reporting Services 建構管理員。

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a>建立與 SQL Server 2008 R2 搭配使用的 System Center Operations Manager 資料庫

如果您想要將 System Center Operations Manager 設定為使用 SQL Server 2008 R2 資料庫，您必須在執行 SQL Server 2008 R2 的電腦上，「手動」建立 Operations Manager 資料庫。 （同樣地，如果您是使用 SQL Server 2005 或 SQL Server 2008 做為後端資料庫，則不需要這些步驟。）

若要手動建立 Operations Manager 資料庫，請執行下列動作：

1.  在 System Center Operations Manager 2007 R2 設定媒體的 [SupportTools\\AMD64] 資料夾中，按兩下 [ **DBCreateWizard**]。

2.  在資料庫設定精靈中，按一下 [**歡迎使用資料庫設定向導]** 頁面上的 **[下一步]**。

3.  在 [**資料庫資訊**] 頁面上，將所有設定保留原樣，然後按 **[下一步]** 。

4.  在 [**管理群組**設定] 頁面上，在 [**管理群組名稱**] 方塊中輸入管理群組的名稱（例如 [ **Lync Server Monitoring**）]，然後按一下 **[下一步]**。

5.  在 [ **Operations Manager 錯誤報表**] 頁面上，按一下 **[下一步]**。

6.  按一下 [**摘要**] 頁面上的 **[完成]**。

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a>建立與 SQL Server 2008 R2 搭配使用的 System Center Operations Manager 資料倉儲

Microsoft Lync Server 2013 隨附三個新的系統中心作業管理員報告：

  - **端對端案例可用性報告**   此報告詳細說明主要 Lync 伺服器服務（例如註冊或目前狀態）的可用性/正常運作時間。

  - **容量報告**   使用效能計數器資訊，此報告會顯示系統元件（例如記憶體可用性與處理器使用量）的趨勢。

  - **元件報告**   ：此報告會列出依 Lync Server 元件分組的上方警示發生器。

若要使用這些新的報表，您必須安裝 System Center Operations Manager 資料倉儲。 （資料倉儲提供對運營資料進行長期儲存）。若要將資料倉儲與 SQL Server 2008 R2 搭配使用，您必須在託管 SQL Server 資料庫的電腦上執行下列步驟：

1.  在 System Center Operations Manager 安裝程式媒體上，在 [\\setup\\SupportTools AMD64] 資料夾中，按兩下 [ **DBCreateWizard**]。

2.  在資料庫設定精靈中，按一下 [**歡迎使用資料庫設定向導]** 頁面上的 **[下一步]**。

3.  在 [**資料庫資訊**] 頁面上，從 [**資料庫類型**] 下拉式清單中選取 [ **Operations Manager 資料倉儲資料庫**]，然後按一下 **[下一步]**。

4.  按一下 [**摘要**] 頁面上的 **[完成]**。

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a>安裝 System Center Operations Manager 主控台

Operations Manager 主控台是用來管理 System Center Operations Manager 的主要工具。 在安裝 Operations Manager 主控台之前，請確認您已安裝受支援的 SQL Server 版本及 SQL Server Reporting Service。 此外，建議您執行 SQL Server 的 Reporting Services Configuration Manager，確認已正確安裝及設定報表服務。

若要安裝 System Center Operations Manager 主控台：

1.  在 System Center Operations Manager 安裝程式媒體上，按兩下 [ **SetupOM**]。

2.  在 System Center Operations Manager 2007 R2 設定中，按一下 [**檢查必備元件**]。

3.  在系統中心作業管理員必備檢視器中，選取要安裝的 System Center 元件：（**伺服器**;**主控台**;和**PowerShell**），然後按一下 [**檢查**]。 確認沒有報告任何封鎖問題，然後按一下 [**關閉**]。 如果已報告封鎖問題，請修正問題，然後按一下 [**檢查**] 以重新執行必要的測試。

4.  在 System Center Operations Manager 安裝程式中，按一下 [**安裝 Operations Manager**]。

5.  在 System Center Operations Manager 安裝程式嚮導中，按一下 [**歡迎使用 System Center Operations Manager 安裝程式嚮導]** 頁面上的 **[下一步]**。

6.  在 [**使用者授權合約**] 頁面上，選取 **[我接受授權協定中的條款**]，然後按 **[下一步]**。

7.  在 [**產品註冊**] 頁面上，于 [**使用者名稱**] 方塊中輸入您的名稱，並在 [**組織**] 方塊中輸入您組織的名稱。 在 [**輸入25位數的 CD 金鑰**] 方塊中，輸入 System Center Operations Manager 產品金鑰，然後按一下 **[下一步]**。

8.  在 [**自訂設定**] 頁面上，選取要安裝的 System Center 選項，然後按 **[下一步]**。 您應該選取 [**管理伺服器**]、[**使用者介面**] 和 [ **Web 主控台**] 進行安裝。 不應選取**資料庫**，也不應該安裝。

9.  在 [ **SC Database Server 實例**] 頁面上，確認安裝 Operations Manager 資料庫的電腦名稱稱出現在 [ **System Center database Server] （系統中心資料庫伺服器**）方塊中。 按一下 **[下一步]**。

10. 在 [**管理伺服器動作帳戶**] 頁面上，選取 [**網域或本機電腦帳戶**]，然後在 [**使用者帳戶**]、[**密碼**] 和 [**網域] 或 [本機電腦**] 方塊中輸入適當的值。 按一下 **[下一步]**。

11. 在 [ **SDK 與 Config 服務帳戶**] 頁面上，選取 [**網域或本機電腦帳戶**]，然後在 [**使用者帳戶**]、[**密碼**] 和 [**網域] 或 [本機電腦**] 方塊中輸入適當的值。 按一下 **[下一步]**。

12. 在 [ **Operations Manager 錯誤報表**] 頁面上，按一下 **[下一步]**。

13. 在 [**客戶經驗改進計畫**] 頁面上，按一下 **[下一步]**。

14. 在 [**準備好安裝程式**] 頁面上，按一下 [**安裝**]。

15. 在 [**完成 System Center Operations Manager 設定**] 頁面上，清除 [**備份加密金鑰**]，然後**啟動 [主控台] 核取方塊**，然後按一下 **[完成]**。

16. 在 System Center Operations Manager 安裝程式中 **，按一下 [** 結束]。

</div>

<div>

## <a name="installing-system-center-reporting-services"></a>安裝 System Center Reporting Services

安裝並設定 System Center Operations Manager 主控台之後，您必須安裝 System Center Reporting Services。 如果您使用的是 SQL Server 2008 R2 作為 Operations Manager 後端資料庫，這表示您必須先對與 SQL Server Reporting Services 相關聯的安全性群組進行暫時的變更。 如果您使用的是 SQL Server 2008 R2，您必須執行下列動作：

1.  按一下 [**開始**]，指向 [系統**管理工具**]，然後按一下 [**伺服器管理員**]。

2.  在 [伺服器管理員] 中，展開 [設定] **，展開 [****本機使用者和群組**]，然後按一下 [**群組**]。

3.  找出下列群組，其中 atl sc-001 代表您電腦的名稱，而 ARCHINST 代表 System Center 資料庫的 SQL Server 實例： **SQLServerReportServerUser $ atl-sc-001 $ MSRS10\_50. ARCHINST**。

4.  以滑鼠右鍵按一下群組，然後按一下 [**重新命名**]。 從組名中刪除** \_50** ，以重新命名群組。 例如： **SQLServerReportServerUser $ atl-sc-001 $ MSRS10。ARCHINST**。

5.  關閉 [伺服器管理員]。

此時，您就可以開始安裝 System Center 報表服務了。 若要執行此動作：

1.  在 System Center Operations Manager 2007 R2 設定媒體上，按兩下 [ **SetupOM**]。

2.  在 System Center Operations Manager 2007 R2 設定中，按一下 [**安裝 Operations Manager 報告**]。

3.  在系統中心作業管理器 2007 R2 報告設定向導中，按一下 [**歡迎使用 Operations Manager 報告設定**] 頁面上的 **[下一步]**。

4.  在 [**使用者授權合約**] 頁面上，選取 **[我接受授權合約的條款**]，然後按 **[下一步]**。

5.  在 [**產品註冊**] 頁面上，確認您的名稱和組織名稱會出現在 [**使用者名稱**] 和 [**組織**] 方塊中，然後按一下 **[下一步]**。

6.  在 [**自訂設定**] 頁面上，按一下 [**報表伺服器**]，然後選取 [**此元件及所有相依元件]，將會安裝在本機磁片磁碟機上**。 按一下 [**資料倉儲**]，然後選取 [**此元件將無法使用**]，然後按一下 **[下一步]**。

7.  在 [連線**至根目錄管理服務器]** 頁面上，于 [**根管理伺服器**] 方塊中輸入 Operations Manager 根管理伺服器的名稱，然後按一下 **[下一步]**。

8.  在 [連線**至 Operations Manager 資料倉儲]** 頁面上，輸入您的資料倉儲位於 [ **Sql server 實例**] 方塊中的 sql server 實例。 （如果您的資料倉儲位於預設實例中，請只需輸入伺服器名稱; 例如： atl-sql-001）。確認 [**名稱**] 方塊中出現 [資料庫名稱**OperationsManagerDW** ]，且 [ **SQL Server 埠**] 方塊中出現 [埠**1433** ]。 按一下 **[下一步]**。

9.  在 [ **SQL Server 報表實例**] 頁面上，從 [**輸入 Sql Server reporting Services 伺服器**] 下拉式清單中選取您的 sql server 報表伺服器，然後按 **[下一步]**。

10. 在 [**資料倉儲寫入帳戶**] 頁面上，于 [**使用者帳戶**] 和 [**密碼**] 方塊中，輸入要為其初始指派寫入權限的使用者名稱和密碼。 從 [**網域**] 下拉式清單中選取使用者的網域，然後按 **[下一步]**。

11. 在 [**資料讀取器帳戶**] 頁面上，輸入要在 SQL Reporting Services 查詢 [**使用者帳戶**] 和 [**密碼**] 方塊中的資料倉儲時所要使用的使用者帳戶名稱和密碼。 從 [**網域**] 下拉式清單中選取 [帳戶網域]，然後按一下 **[下一步]**。

12. 在 [**運算元據報表**] 頁面上，按一下 **[下一步]**。

13. 在 [ **Microsoft Update** ] 頁面上，按一下 **[下一步]**。

14. 在 [**準備好安裝程式**] 頁面上，按一下 [**安裝**]。

15. 在 [**完成 Operations Manager 報告元件安裝程式嚮導]** 頁面上，按一下 **[完成]**。

16. 在 System Center Operations Manager 2007 R2 設定中，**按一下 [** 結束]。

安裝 System Center 報表之後，您可以使用下列程式來重設與 SQL Server 報告相關聯之安全性群組的名稱。 同樣地，只有在您使用 SQL Server 時，才需要執行此程式：

1.  按一下 [**開始**]，指向 [系統**管理工具**]，然後按一下 [**伺服器管理員**]。

2.  在 [伺服器管理員] 中，展開 [設定] **，展開 [****本機使用者和群組**]，然後按一下 [**群組**]。

3.  找出下列群組，其中 atl sc-001 代表您電腦的名稱，而 ARCHINST 代表封存與監控資料庫的 SQL Server 實例： **SQLServerReportServerUser $ atl-sc-001 $ MSRS10。ARCHINST**。

4.  以滑鼠右鍵按一下群組，然後按一下 [**重新命名**]。 將** \_50**新增至組名的結尾，在 SQL Server 實例名稱前面加上，即可重新命名群組。 例如： **SQLServerReportServerUser $ atl-sc-001 $ MSRS10\_50. ARCHINST**。

5.  關閉 [伺服器管理員]。

如果 System Center 操作主控台已開啟，您將需要關閉該應用程式，然後重新開機它;如果您不這麼做，[**報告**] 索引標籤就不會出現在 [操作] 主控台使用者介面中。 請注意，第一次重新開機作業主控台之後，可能需要幾分鐘的時間，所有的監視報告才會出現在 [**報告**] 索引標籤上。

</div>

</div>

<span> </span>

</div>

</div>

</div>

