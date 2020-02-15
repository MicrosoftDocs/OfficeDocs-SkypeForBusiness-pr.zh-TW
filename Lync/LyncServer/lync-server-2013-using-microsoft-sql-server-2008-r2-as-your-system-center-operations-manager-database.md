---
title: Lync Server 2013： 使用 Microsoft SQL Server 2008 R2 與 System Center Operations Manager 資料庫
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
ms.openlocfilehash: 6ad7854043eb85db7b5d260d57beed26746160f5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a><span data-ttu-id="dff34-102">使用 Microsoft SQL Server 2008 R2 當成 System Center Operations Manager 資料庫 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dff34-102">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dff34-103">_**上次修改主題：** 2013年-07-29_</span><span class="sxs-lookup"><span data-stu-id="dff34-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="dff34-104">若要使用 SQL Server 2008 R2 作為您的後端資料庫，請完成本主題中詳述的步驟。</span><span class="sxs-lookup"><span data-stu-id="dff34-104">To use SQL Server 2008 R2 as your back-end database, complete the steps detailed in this topic.</span></span>

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a><span data-ttu-id="dff34-105">設定 SQL Server 2008 R2 和 SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="dff34-105">Configuring SQL Server 2008 R2 and SQL Server Reporting Services</span></span>

<span data-ttu-id="dff34-106">在您開始安裝 System Center Operations Manager 之前您必須對兩項變更您的 SQL Server 2008 R2 和 SQL Server Reporting Services 組態。</span><span class="sxs-lookup"><span data-stu-id="dff34-106">Before you begin installing System Center Operations Manager you must make two changes to your SQL Server 2008 R2 and your SQL Server Reporting Services configuration.</span></span> <span data-ttu-id="dff34-107">（這些變更是必要的只有在您使用 SQL Server 2008 R2 與您的 Operations Manager 資料庫函式）。首先，依下列方式將主控您 Operations Manager 資料庫的電腦上：</span><span class="sxs-lookup"><span data-stu-id="dff34-107">(These changes are required only if you are using SQL Server 2008 R2 as your Operations Manager database.) First, do the following on the computer that will host your Operations Manager database:</span></span>

1.  <span data-ttu-id="dff34-108">按一下 [開始]\*\*\*\*，然後按 [執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-108">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="dff34-109">在 [**執行**] 對話方塊中，輸入**c:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50.ARCHINST\\Reporting Services\\ReportServer** ，然後按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="dff34-109">In the **Run** dialog box, type **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50.ARCHINST\\Reporting Services\\ReportServer** and then press ENTER.</span></span>

3.  <span data-ttu-id="dff34-110">在 **ReportServer** 資料夾中，以 [記事本] 或任何其他文字編輯器來開啟 **rsreportserver.config** 檔案。</span><span class="sxs-lookup"><span data-stu-id="dff34-110">In the **ReportServer** folder, open the file **rsreportserver.config** in Notepad or any other text editor.</span></span>

4.  <span data-ttu-id="dff34-111">您會在靠近檔案開頭的地方，看到一連串的 "Add Key" 節點。</span><span class="sxs-lookup"><span data-stu-id="dff34-111">Near the beginning of the file you will see a series of "Add Key" nodes.</span></span> <span data-ttu-id="dff34-112">尋找開始的項目**\<新增機碼 ="SecureConnectionLevel 」** 並設定為**0**的值：</span><span class="sxs-lookup"><span data-stu-id="dff34-112">Find the entry that begins **\<Add Key="SecureConnectionLevel"** and set the value to **0**:</span></span>
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  <span data-ttu-id="dff34-113">儲存 **rsreportserver.config** 檔案，然後關閉文字編輯器。</span><span class="sxs-lookup"><span data-stu-id="dff34-113">Save the file **rsreportserver.config** and then close your text editor.</span></span>

<span data-ttu-id="dff34-p103">更新報告伺服器組態檔之後，您必須指派正確的憑證給 SQL Server Reporting Services。若要執行這項作業，請完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="dff34-p103">After updating the Report Server configuration file you must then assign the correct certificate to SQL Server Reporting Services. To do that:</span></span>

1.  <span data-ttu-id="dff34-116">按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft SQL Server 2008 R2**、 [**組態工具**]，然後按一下**Reporting Services 組態管理員**。</span><span class="sxs-lookup"><span data-stu-id="dff34-116">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="dff34-117">在 [Reporting Services 組態連接]\*\*\*\* 對話方塊中，確定您的伺服器名稱出現在 [伺服器名稱]\*\*\*\* 方塊中。</span><span class="sxs-lookup"><span data-stu-id="dff34-117">In the **Reporting Services Configuration Connection** dialog box, make sure that the name of your server appears in the **Server Name** box.</span></span> <span data-ttu-id="dff34-118">從 [**報表伺服器執行個體**] 下拉式清單中選取將主控您 Operations Manager 資料庫 (例如， **ARCHINST**) 的 SQL Server 執行個體，然後按一下 [**連線**]。</span><span class="sxs-lookup"><span data-stu-id="dff34-118">Select the SQL Server instance that will host your Operations Manager database (for example, **ARCHINST**) from the **Report Server Instance** drop-down list and then click **Connect**.</span></span>

3.  <span data-ttu-id="dff34-119">在 Reporting Services 組態管理員中，按一下 [Web 服務 URL]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-119">In Reporting Services Configuration Manager, click **Web Service URL**.</span></span>

4.  <span data-ttu-id="dff34-p105">在「Web 服務 URL」\*\*\*\* 頁面上，從 [SSL 憑證]\*\*\*\* 下拉式清單中選取要用於 Reporting Services 的憑證，然後按一下 [套用]\*\*\*\*。幾秒鐘之後，您就會看到 [報告伺服器 Web 服務 URL]\*\*\*\* 底下列出一對 URL。</span><span class="sxs-lookup"><span data-stu-id="dff34-p105">On the **Web Service URL** page, select the certificate to be used for your Reporting Services from the **SSL Certificate** dropdown list and then click **Apply**. After a few seconds, you will see a pair of URLs listed under **Report Server Web Service URLs**.</span></span>

5.  <span data-ttu-id="dff34-122">在兩個 URL 上都按一下，以確認您可以存取 SQL Server Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="dff34-122">Click both of the URLs to verify that you can access SQL Server Reporting Services.</span></span>

6.  <span data-ttu-id="dff34-123">關閉 Reporting Services 組態管理員。</span><span class="sxs-lookup"><span data-stu-id="dff34-123">Close Reporting Services Configuration Manager.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="dff34-124">建立使用 System Center Operations Manager 資料庫與 SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="dff34-124">Creating a System Center Operations Manager database for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="dff34-125">如果您想要設定為使用 SQL Server 2008 R2 資料庫的 System Center Operations Manager，您將需要 「 手動 」 建立在執行 SQL Server 2008 R2 的電腦上的 [Operations Manager 資料庫。</span><span class="sxs-lookup"><span data-stu-id="dff34-125">If you want to configure System Center Operations Manager to use a SQL Server 2008 R2 database, you will need to "manually" create the Operations Manager database on the computer running SQL Server 2008 R2.</span></span> <span data-ttu-id="dff34-126">（同樣地，這些步驟是不需要如果您使用 SQL Server 2005 或 SQL Server 2008 與您的後端資料庫）。</span><span class="sxs-lookup"><span data-stu-id="dff34-126">(Again, these steps are not required if you are using SQL Server 2005 or SQL Server 2008 as your back-end database.)</span></span>

<span data-ttu-id="dff34-127">若要以手動方式建立 Operations Manager 資料庫執行下列：</span><span class="sxs-lookup"><span data-stu-id="dff34-127">To manually create an Operations Manager database do the following:</span></span>

1.  <span data-ttu-id="dff34-128">System Center Operations Manager 2007 R2 上安裝媒體，SupportTools\\AMD64] 資料夾中，按兩下**DBCreateWizard.exe**。</span><span class="sxs-lookup"><span data-stu-id="dff34-128">On the System Center Operations Manager 2007 R2 setup media, in the SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="dff34-129">在 [資料庫設定精靈] 的「歡迎使用資料庫設定精靈」\*\*\*\* 頁面上，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-129">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="dff34-130">在「資料庫資訊」\*\*\*\* 頁面上，將所有設定保留原狀，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-130">On the **Database Information** page leave all the settings as-is and then click **Next**</span></span>

4.  <span data-ttu-id="dff34-131">在 [**管理群組設定**] 頁面**管理群組名稱**] 方塊中輸入管理群組 （例如， **Lync Server 監視**） 的名稱，然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="dff34-131">On the **Management Group Configuration** page type a name for your Management Group (for example, **Lync Server Monitoring**) in the **Management Group name** box and then click **Next**.</span></span>

5.  <span data-ttu-id="dff34-132">在「Operations Manager 錯誤報告」\*\*\*\* 頁面上，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-132">On the **Operations Manager Error Reports** page click **Next**.</span></span>

6.  <span data-ttu-id="dff34-133">在「摘要」\*\*\*\* 頁面上，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-133">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="dff34-134">System Center Operations Manager 資料倉儲以用於建立與 SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="dff34-134">Creating a System Center Operations Manager data warehouse for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="dff34-135">Microsoft Lync Server 2013 隨附三個新的 System Center Operations Manager 報告：</span><span class="sxs-lookup"><span data-stu-id="dff34-135">Microsoft Lync Server 2013 ships with three new System Center Operations Manager reports:</span></span>

  - <span data-ttu-id="dff34-136">**端對端案例可用性報告**   此報告詳述可用性/上線時間，例如註冊或目前狀態的 Lync Server 服務的索引鍵。</span><span class="sxs-lookup"><span data-stu-id="dff34-136">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="dff34-137">**容量報告**   使用效能計數器資訊，這份報告顯示系統元件，例如記憶體可用性及處理器使用量的趨勢。</span><span class="sxs-lookup"><span data-stu-id="dff34-137">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="dff34-138">**元件報告**   此報告會列出依 Lync Server 元件分組的首要警示產生器。</span><span class="sxs-lookup"><span data-stu-id="dff34-138">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="dff34-139">若要使用這些新的報告，您必須安裝 System Center Operations Manager 資料倉儲。</span><span class="sxs-lookup"><span data-stu-id="dff34-139">In order to use these new reports you must install a System Center Operations Manager data warehouse.</span></span> <span data-ttu-id="dff34-140">（資料倉儲提供針對長期儲存作業資料）。若要使用的資料倉儲與 SQL Server 2008 R2 您必須執行下列步驟在主控 SQL Server 資料庫的電腦上：</span><span class="sxs-lookup"><span data-stu-id="dff34-140">(A data warehouse provides for long-term storage of operations data.) To use a data warehouse with SQL Server 2008 R2 you must carry out the following steps on the computer that hosts your SQL Server database:</span></span>

1.  <span data-ttu-id="dff34-141">在 System Center Operations Manager 上安裝媒體上的，安裝程式中\\SupportTools\\AMD64] 資料夾中，按兩下**DBCreateWizard.exe**。</span><span class="sxs-lookup"><span data-stu-id="dff34-141">On the System Center Operations Manager setup media, in the Setup\\SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="dff34-142">在 [資料庫設定精靈] 的「歡迎使用資料庫設定精靈」\*\*\*\* 頁面上，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-142">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="dff34-143">在「資料庫資訊」\*\*\*\* 頁面上，從 [資料庫類型]\*\*\*\* 下拉式清單中選取 [Operations Manager 資料倉儲資料庫]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-143">On the **Database Information** page, select **Operations Manager Data Warehouse Database** from the **Database Type** dropdown list and then click **Next**.</span></span>

4.  <span data-ttu-id="dff34-144">在「摘要」\*\*\*\* 頁面上，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-144">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a><span data-ttu-id="dff34-145">安裝 System Center Operations Manager 主控台</span><span class="sxs-lookup"><span data-stu-id="dff34-145">Installing the System Center Operations Manager console</span></span>

<span data-ttu-id="dff34-146">在 Operations Manager 主控台是用來管理 System Center Operations Manager 的主要工具。</span><span class="sxs-lookup"><span data-stu-id="dff34-146">The Operations Manager console is the primary tool used to manage System Center Operations Manager.</span></span> <span data-ttu-id="dff34-147">安裝 Operations Manager 主控台之前，請確定您已安裝支援的版本的 SQL Server 以及 SQL Server Reporting Service。</span><span class="sxs-lookup"><span data-stu-id="dff34-147">Before you install the Operations Manager console, make sure that you have installed a supported version of SQL Server along with the SQL Server Reporting Service.</span></span> <span data-ttu-id="dff34-148">此外，也建議您執行 SQL Server 的 Reporting Services 組態管理員，以確認 Reporting Service 已正確安裝及設定。</span><span class="sxs-lookup"><span data-stu-id="dff34-148">It is also recommended that you run SQL Server's Reporting Services Configuration Manager to verify that the Reporting Service has been correctly installed and configured.</span></span>

<span data-ttu-id="dff34-149">若要安裝 System Center Operations Manager 主控台：</span><span class="sxs-lookup"><span data-stu-id="dff34-149">To install the System Center Operations Manager console:</span></span>

1.  <span data-ttu-id="dff34-150">在 System Center Operations Manager 安裝媒體上，按兩下 [ **SetupOM.exe**]。</span><span class="sxs-lookup"><span data-stu-id="dff34-150">On the System Center Operations Manager setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="dff34-151">在 System Center Operations Manager 2007 R2 安裝程式中，按一下 [**檢查必要條件**]。</span><span class="sxs-lookup"><span data-stu-id="dff34-151">In System Center Operations Manager 2007 R2 Setup, click **Check Prerequisites**.</span></span>

3.  <span data-ttu-id="dff34-152">系統管理中心 Operations Manager 必要條件檢視器中，選取要安裝 System Center 的元件: (**伺服器**;**主控台**;和**PowerShell**），然後按一下 [**檢查**。</span><span class="sxs-lookup"><span data-stu-id="dff34-152">In the System Center Operations Manager Prerequisite Viewer, select the System Center components to be installed: (**Server**; **Console**; and **PowerShell**) and then click **Check**.</span></span> <span data-ttu-id="dff34-153">確認沒有報告任何封鎖問題，然後按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-153">Verify that no blocking issues have been reported and then click **Close**.</span></span> <span data-ttu-id="dff34-154">如果有報告封鎖問題，請更正問題，然後按一下 [檢查]\*\*\*\*，重新執行必要條件測試。</span><span class="sxs-lookup"><span data-stu-id="dff34-154">If a blocking issue has been reported, correct the problem and then click **Check** to re-run the prerequisite testing.</span></span>

4.  <span data-ttu-id="dff34-155">在 System Center Operations Manager 安裝程式，按一下 [**安裝 Operations Manager**。</span><span class="sxs-lookup"><span data-stu-id="dff34-155">In System Center Operations Manager Setup, click **Install Operations Manager**.</span></span>

5.  <span data-ttu-id="dff34-156">在 System Center Operations Manager 安裝精靈]**歡迎使用系統管理中心 Operations Manager 安裝精靈**] 頁面上，按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="dff34-156">In the System Center Operations Manager Setup wizard, on the **Welcome to the System Center Operations Manager Setup Wizard** page, click **Next**.</span></span>

6.  <span data-ttu-id="dff34-157">在「使用者授權合約」\*\*\*\* 頁面上，選取 [我接受授權合約中的條款]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-157">On the **End-User License Agreement** page, select **I accept the terms in the license agreement** and then click **Next**.</span></span>

7.  <span data-ttu-id="dff34-158">在「產品註冊」\*\*\*\* 頁面上的 [使用者名稱]\*\*\*\* 方塊中，輸入您的名稱，並且在 [組織]\*\*\*\* 方塊中輸入組織的名稱。</span><span class="sxs-lookup"><span data-stu-id="dff34-158">On the **Product Registration** page, type your name in the **User Name** box and name of your organization in the **Organization** box.</span></span> <span data-ttu-id="dff34-159">**輸入您 25 位數的產品識別碼**] 方塊中輸入您的 System Center Operations Manager 產品金鑰，然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="dff34-159">Type your System Center Operations Manager product key in the **Enter your 25 digit CD Key** box and then click **Next**.</span></span>

8.  <span data-ttu-id="dff34-p111">在「自訂安裝程式」\*\*\*\* 頁面上，選取所要安裝的 System Center 選項，然後按 [下一步]\*\*\*\*。您應選取 [管理伺服器]\*\*\*\*、[資料庫使用者介面]\*\*\*\* 及 [Web 主控台]\*\*\*\* 以進行安裝。不應選取 [資料庫]\*\*\*\*，也不應安裝。</span><span class="sxs-lookup"><span data-stu-id="dff34-p111">On the **Custom Setup** page select the System Center options to be installed and then click **Next**. You should select **Management Server**, **User Interfaces**, and **Web Console** to be installed. **Database** should not be selected and should not be installed.</span></span>

9.  <span data-ttu-id="dff34-163">在 [ **SC 資料庫伺服器執行個體**] 頁面上，確認安裝 Operations Manager 資料庫的電腦名稱會出現在**System Center 資料庫伺服器**] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="dff34-163">On the **SC Database Server Instance** page, verify that the name of the computer where the Operations Manager databases are installed appears in the **System Center Database Server** box.</span></span> <span data-ttu-id="dff34-164">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-164">Click **Next**.</span></span>

10. <span data-ttu-id="dff34-p113">在「管理伺服器動作帳戶」\*\*\*\* 頁面上，選取 [網域或本機電腦帳戶]\*\*\*\*，然後在 [使用者帳戶]\*\*\*\*、[密碼]\*\*\*\* 及 [網域或本機電腦]\*\*\*\* 方塊中輸入適當的值。按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-p113">On the **Management Server Action Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes. Click **Next**.</span></span>

11. <span data-ttu-id="dff34-p114">在「SDK 和設定服務帳戶」\*\*\*\* 頁面上，選取 [網域或本機電腦帳戶]\*\*\*\*，然後在 [使用者帳戶]\*\*\*\*、[密碼]\*\*\*\* 及 [網域或本機電腦]\*\*\*\* 方塊中輸入適當的值。按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-p114">On the **SDK and Config Service Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes. Click **Next**.</span></span>

12. <span data-ttu-id="dff34-169">在「Operations Manager 錯誤報告」\*\*\*\* 頁面上，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-169">On the **Operations Manager Error Reports** page click **Next**.</span></span>

13. <span data-ttu-id="dff34-170">在「客戶經驗改進計畫」\*\*\*\* 頁面上，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-170">On the **Customer Experience Improvement Program** page click **Next**.</span></span>

14. <span data-ttu-id="dff34-171">在「已完成安裝程式的準備工作」\*\*\*\* 頁面上，按一下 [安裝]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-171">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="dff34-172">在「正在完成 System Center Operations Manager 安裝程式」\*\*\*\* 頁面上，清除 [備份加密金鑰]\*\*\*\* 及 [啟動主控台]\*\*\*\* 核取方塊，然後按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-172">On the **Completing the System Center Operations Manager Setup** page, clear the **Backup Encryption Key** and **Start the console checkboxes** and then click **Finish**.</span></span>

16. <span data-ttu-id="dff34-173">在 System Center Operations Manager 安裝程式中按一下 [**結束**]。</span><span class="sxs-lookup"><span data-stu-id="dff34-173">In System Center Operations Manager Setup click **Exit**.</span></span>

</div>

<div>

## <a name="installing-system-center-reporting-services"></a><span data-ttu-id="dff34-174">安裝 System Center Reporting Services</span><span class="sxs-lookup"><span data-stu-id="dff34-174">Installing System Center Reporting Services</span></span>

<span data-ttu-id="dff34-175">安裝和設定 System Center Operations Manager 主控台之後，您必須再安裝 System Center Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="dff34-175">After installing and configuring the System Center Operations Manager console you must then install System Center Reporting Services.</span></span> <span data-ttu-id="dff34-176">如果您使用 SQL Server 2008 R2 與您 Operations Manager 的後端資料庫，這表示，您必須先對暫時變更 SQL Server Reporting Services 與相關聯的 [安全性] 群組。</span><span class="sxs-lookup"><span data-stu-id="dff34-176">If you are using SQL Server 2008 R2 as your Operations Manager back-end database, that means that you must first make a temporary change to the security group associated with SQL Server Reporting Services.</span></span> <span data-ttu-id="dff34-177">如果您使用 SQL Server 2008 R2，您必須執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="dff34-177">If you are using SQL Server 2008 R2, you must do the following:</span></span>

1.  <span data-ttu-id="dff34-178">按一下 [開始]\*\*\*\*，指向 [系統管理工具]\*\*\*\*，然後按一下 [伺服器管理員]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-178">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="dff34-179">在伺服器管理員中，依序展開 [設定]\*\*\*\* 及 [本機使用者和群組]\*\*\*\*，然後按一下 [群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-179">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="dff34-180">尋找下列群組，其中 atl-sc-001 代表您的電腦名稱，而 ARCHINST 代表 System Center 資料庫的 SQL Server 執行個體： **SQLServerReportServerUser$ atl sc 001$ MSRS10\_50.ARCHINST**。</span><span class="sxs-lookup"><span data-stu-id="dff34-180">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the System Center database: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

4.  <span data-ttu-id="dff34-181">以滑鼠右鍵按一下該群組，然後按一下 [重新命名]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-181">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="dff34-182">重新命名群組刪除**\_50**和群組名稱。</span><span class="sxs-lookup"><span data-stu-id="dff34-182">Rename the group by deleting **\_50** from the group name.</span></span> <span data-ttu-id="dff34-183">例如： **SQLServerReportServerUser$ atl-sc-001$ MSRS10。ARCHINST**。</span><span class="sxs-lookup"><span data-stu-id="dff34-183">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

5.  <span data-ttu-id="dff34-184">關閉伺服器管理員。</span><span class="sxs-lookup"><span data-stu-id="dff34-184">Close Server Manager.</span></span>

<span data-ttu-id="dff34-p117">這時候，您已經準備好可以安裝 System Center Reporting Services。若要執行這項作業，請完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="dff34-p117">At this point you are ready to install System Center Reporting Services. To do this:</span></span>

1.  <span data-ttu-id="dff34-187">在 System Center Operations Manager 2007 R2 安裝媒體上，按兩下 [ **SetupOM.exe**]。</span><span class="sxs-lookup"><span data-stu-id="dff34-187">On the System Center Operations Manager 2007 R2 Setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="dff34-188">在 System Center Operations Manager 2007 R2 安裝程式，按一下 [**安裝 Operations Manager 報告**]。</span><span class="sxs-lookup"><span data-stu-id="dff34-188">In System Center Operations Manager 2007 R2 Setup, click **Install Operations Manager Reporting**.</span></span>

3.  <span data-ttu-id="dff34-189">在 System Center Operations Manager 2007 R2 報告安裝程式精靈]**歡迎使用 Operations Manager 報告安裝程式**] 頁面上，按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="dff34-189">In the System Center Operations Manager 2007 R2 Reporting Setup wizard, on the **Welcome to Operations Manager Reporting Setup** page, click **Next**.</span></span>

4.  <span data-ttu-id="dff34-190">在「使用者授權合約」\*\*\*\* 頁面上，選取 [我接受授權合約中的條款]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-190">On the **End-user License Agreement** page select **I accept the terms of the license agreement** and then click **Next**.</span></span>

5.  <span data-ttu-id="dff34-191">在「產品註冊」\*\*\*\* 頁面上，確定您的名稱和組織的名稱分別出現在 [使用者名稱]\*\*\*\* 和 [組織]\*\*\*\* 方塊中，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-191">On the **Product Registration** page, ensure that your name and the name of your organization appear in the **User Name** and **Organization** boxes and then click **Next**.</span></span>

6.  <span data-ttu-id="dff34-p118">在「自訂安裝程式」\*\*\*\* 頁面上，按一下 [報告伺服器]\*\*\*\*，並選取 [這個元件以及所有相依的元件會安裝到本機硬碟]\*\*\*\*。按一下 [資料倉儲]\*\*\*\*，並選取 [這個元件將無法使用]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-p118">On the **Custom Setup** page, click **Reporting Server** and select **This component, and all dependent components, will be installed on local disk drive**. Click **Data Warehouse** and select **This component will not be available**, and then click **Next**.</span></span>

7.  <span data-ttu-id="dff34-194">在「連線至 Root Management Server」\*\*\*\* 頁面上的 [Root Management Server]\*\*\*\* 方塊中，輸入 Operations Manager Root Management Server 的名稱，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-194">On the **Connect to the Root Management Server** page, type the name of your Operations Manager root management server in the **Root Management Server** box and then click **Next**.</span></span>

8.  <span data-ttu-id="dff34-p119">在「連線到 Operations Manager 資料倉儲」\*\*\*\* 頁面上的 [SQL Server 執行個體]\*\*\*\* 方塊中，輸入資料倉儲所在的 SQL Server 執行個體。(如果資料倉儲位在預設執行個體中，則直接輸入伺服器名稱即可；例如：atl-sql-001。) 確認資料庫名稱 **OperationsManagerDW** 出現在 [名稱]\*\*\*\* 方塊中，而且連接埠 **1433** 出現在 [SQL Server 連接埠]\*\*\*\* 方塊中。按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-p119">On the **Connect to the Operations Manager Data Warehouse** page, type the SQL Server instance where your data warehouse is located in the **SQL Server Instance** box. (If your data warehouse is located in the Default instance then simply type the server name; for example: atl-sql-001.) Verify that the database name **OperationsManagerDW** appears in the **Name** box, and that port **1433** appears in the **SQL Server port** box. Click **Next**.</span></span>

9.  <span data-ttu-id="dff34-198">在「SQL Server 報告執行個體」\*\*\*\* 頁面上，從 [輸入 SQL Server Reporting Services 伺服器]\*\*\*\* 下拉式清單中選取 SQL Server 報告伺服器，然後 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-198">On the **SQL Server Reporting Instance** page, select your SQL Server reporting server from the **Enter the SQL Server Reporting Services Server** dropdown list and then click **Next**.</span></span>

10. <span data-ttu-id="dff34-p120">在「資料倉儲寫入帳戶」\*\*\*\* 頁面上的 [使用者帳戶]\*\*\*\* 和 [密碼]\*\*\*\* 方塊中，輸入一開始要為其指派資料倉儲寫入權限的使用者名稱和密碼。從 [網域]\*\*\*\* 下拉式清單中選取使用者的網域，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-p120">On the **Data Warehouse Write Account** page, enter the name and password of the user to be initially assigned write permissions to the data warehouse in the **User Account** and **Password** boxes. Select the user's domain from the **Domain** dropdown list and then click **Next**.</span></span>

11. <span data-ttu-id="dff34-p121">在「資料讀取器帳戶」\*\*\*\* 頁面上的 [使用者帳戶]\*\*\*\* 和 [密碼]\*\*\*\* 方塊中，輸入當 SQL Reporting Services 查詢資料倉儲時，所要使用之使用者帳戶的名稱和密碼。從 [網域]\*\*\*\* 下拉式清單中選取帳戶網域，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-p121">On the **Data Reader Account** page, enter the name and password of the user account to be used when SQL Reporting Services queries the data warehouse in the **User Account** and **Password** boxes. Select the account domain from the **Domain** dropdown list and then click **Next**.</span></span>

12. <span data-ttu-id="dff34-203">在「操作資料報告」\*\*\*\* 頁面上，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-203">On the **Operational Data Reports** page, click **Next**.</span></span>

13. <span data-ttu-id="dff34-204">在「Microsoft Update」\*\*\*\* 頁面上，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-204">On the **Microsoft Update** page, click **Next**.</span></span>

14. <span data-ttu-id="dff34-205">在「已完成安裝程式的準備工作」\*\*\*\* 頁面上，按一下 [安裝]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-205">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="dff34-206">在「正在完成 Operations Manager 報告元件安裝精靈」\*\*\*\* 頁面上，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-206">On the **Completing the Operations Manager Reporting Components Setup Wizard** page, click **Finish**.</span></span>

16. <span data-ttu-id="dff34-207">在 System Center Operations Manager 2007 R2 安裝程式中，按一下 [**結束**]。</span><span class="sxs-lookup"><span data-stu-id="dff34-207">In System Center Operations Manager 2007 R2 Setup, click **Exit**.</span></span>

<span data-ttu-id="dff34-208">安裝 System Center reporting 之後您再使用下列程序重設與 SQL Server 報表相關聯的 [安全性] 群組的名稱。</span><span class="sxs-lookup"><span data-stu-id="dff34-208">After System Center reporting has been installed you then use the following procedure to reset the name of the security group associated with SQL Server reporting.</span></span> <span data-ttu-id="dff34-209">同樣地，此程序是只需要如果您使用 SQL Server:</span><span class="sxs-lookup"><span data-stu-id="dff34-209">Again, this procedure is only required if you are using SQL Server:</span></span>

1.  <span data-ttu-id="dff34-210">按一下 [開始]\*\*\*\*，指向 [系統管理工具]\*\*\*\*，然後按一下 [伺服器管理員]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-210">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="dff34-211">在伺服器管理員中，依序展開 [設定]\*\*\*\* 及 [本機使用者和群組]\*\*\*\*，然後按一下 [群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-211">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="dff34-212">尋找下列群組，其中 atl-sc-001 代表您的電腦名稱，而 ARCHINST 代表封存及監控資料庫的 SQL Server 執行個體： SQLServerReportServerUser$ atl-sc-001$ MSRS10 **。ARCHINST**。</span><span class="sxs-lookup"><span data-stu-id="dff34-212">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the archiving and monitoring databases: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

4.  <span data-ttu-id="dff34-213">以滑鼠右鍵按一下該群組，然後按一下 [重新命名]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dff34-213">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="dff34-214">重新命名群組新增**\_50**名稱結尾的群組，以滑鼠右鍵之前的 SQL Server 執行個體名稱。</span><span class="sxs-lookup"><span data-stu-id="dff34-214">Rename the group by adding **\_50** to the end of the group name, right before the SQL Server instance name.</span></span> <span data-ttu-id="dff34-215">例如： **SQLServerReportServerUser$ atl sc 001$ MSRS10\_50.ARCHINST**。</span><span class="sxs-lookup"><span data-stu-id="dff34-215">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

5.  <span data-ttu-id="dff34-216">關閉伺服器管理員。</span><span class="sxs-lookup"><span data-stu-id="dff34-216">Close Server Manager.</span></span>

<span data-ttu-id="dff34-p124">如果 System Center 操作主控台開啟，則您需要關閉應用程式，然後再重新啟動；如果不這麼做，[報告]\*\*\*\* 索引標籤不會出現在操作主控台使用者介面中。請注意，第一次重新啟動操作主控台之後，可能需要幾分鐘的時間，監視報告才會全部出現在 [報告]\*\*\*\* 索引標籤中。</span><span class="sxs-lookup"><span data-stu-id="dff34-p124">If the System Center Operations Console is open you will need to close the application and then restart it; if you do not do this the **Reporting** tab will not appear in the Operations Console user interface. Note that, after restarting the Operations Console the first time, it could take several minutes before all the Monitoring Reports appear on the **Reporting** tab.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

