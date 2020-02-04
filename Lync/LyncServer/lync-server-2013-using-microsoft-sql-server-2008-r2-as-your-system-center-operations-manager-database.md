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
ms.openlocfilehash: 27516e7ca6c3fb70a01b7c1d245054d515ae351b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a><span data-ttu-id="41160-102">使用 Microsoft SQL Server 2008 R2 作為 Lync Server 2013 的 System Center Operations Manager 資料庫</span><span class="sxs-lookup"><span data-stu-id="41160-102">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41160-103">_**主題上次修改日期：** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="41160-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="41160-104">若要使用 SQL Server 2008 R2 作為後端資料庫，請完成本主題中詳細說明的步驟。</span><span class="sxs-lookup"><span data-stu-id="41160-104">To use SQL Server 2008 R2 as your back-end database, complete the steps detailed in this topic.</span></span>

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a><span data-ttu-id="41160-105">正在設定 SQL Server 2008 R2 與 SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="41160-105">Configuring SQL Server 2008 R2 and SQL Server Reporting Services</span></span>

<span data-ttu-id="41160-106">您必須先對 SQL Server 2008 R2 以及 SQL Server Reporting Services 設定進行兩個變更，才能開始安裝 System Center 作業管理器。</span><span class="sxs-lookup"><span data-stu-id="41160-106">Before you begin installing System Center Operations Manager you must make two changes to your SQL Server 2008 R2 and your SQL Server Reporting Services configuration.</span></span> <span data-ttu-id="41160-107">（只有當您使用 SQL Server 2008 R2 作為 Operations Manager 資料庫時，才需要進行這些變更。）首先，請在將裝載 Operations Manager 資料庫的電腦上執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="41160-107">(These changes are required only if you are using SQL Server 2008 R2 as your Operations Manager database.) First, do the following on the computer that will host your Operations Manager database:</span></span>

1.  <span data-ttu-id="41160-108">按一下 [**開始**]，然後按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="41160-108">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="41160-109">在 [**執行**] 對話方塊中，**輸入 C\\： Program\\Files Microsoft SQL\\ Server\_MSRS10 50.\\ARCHINST Reporting\\Services ReportServer** ，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="41160-109">In the **Run** dialog box, type **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50.ARCHINST\\Reporting Services\\ReportServer** and then press ENTER.</span></span>

3.  <span data-ttu-id="41160-110">在 [ **ReportServer** ] 資料夾中，在 [記事本] 或任何其他文字編輯器中開啟 [檔案**rsreportserver** ]。</span><span class="sxs-lookup"><span data-stu-id="41160-110">In the **ReportServer** folder, open the file **rsreportserver.config** in Notepad or any other text editor.</span></span>

4.  <span data-ttu-id="41160-111">在靠近檔案開頭的位置，您會看到一系列的 "Add Key" （新增鍵）節點。</span><span class="sxs-lookup"><span data-stu-id="41160-111">Near the beginning of the file you will see a series of "Add Key" nodes.</span></span> <span data-ttu-id="41160-112">找出開始\*\* \<新增索引鍵 = "SecureConnectionLevel"\*\* 的專案，並將值設為**0**：</span><span class="sxs-lookup"><span data-stu-id="41160-112">Find the entry that begins **\<Add Key="SecureConnectionLevel"** and set the value to **0**:</span></span>
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  <span data-ttu-id="41160-113">儲存檔**rsreportserver** ，然後關閉您的文字編輯器。</span><span class="sxs-lookup"><span data-stu-id="41160-113">Save the file **rsreportserver.config** and then close your text editor.</span></span>

<span data-ttu-id="41160-114">更新報表伺服器設定檔之後，您必須將正確的憑證指派給 SQL Server Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="41160-114">After updating the Report Server configuration file you must then assign the correct certificate to SQL Server Reporting Services.</span></span> <span data-ttu-id="41160-115">若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="41160-115">To do that:</span></span>

1.  <span data-ttu-id="41160-116">按一下 [**開始**]，按一下 [**所有程式**]，按一下 **[Microsoft SQL Server 2008 R2**]，按一下 [設定**工具**]，然後按一下 [ **Reporting Services Configuration Manager**]。</span><span class="sxs-lookup"><span data-stu-id="41160-116">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="41160-117">在 [ **Reporting Services**設定連線] 對話方塊中，確定您的伺服器名稱出現在 [**伺服器名稱**] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="41160-117">In the **Reporting Services Configuration Connection** dialog box, make sure that the name of your server appears in the **Server Name** box.</span></span> <span data-ttu-id="41160-118">從 [**報表伺服器實例**] 下拉式清單中選取將承載 Operations Manager 資料庫的 SQL Server 實例（例如**ARCHINST**），然後按一下 **[連線]**。</span><span class="sxs-lookup"><span data-stu-id="41160-118">Select the SQL Server instance that will host your Operations Manager database (for example, **ARCHINST**) from the **Report Server Instance** drop-down list and then click **Connect**.</span></span>

3.  <span data-ttu-id="41160-119">在 Reporting Services 組態管理員中，按一下 [ **Web 服務 URL**]。</span><span class="sxs-lookup"><span data-stu-id="41160-119">In Reporting Services Configuration Manager, click **Web Service URL**.</span></span>

4.  <span data-ttu-id="41160-120">在 [ **Web 服務 URL** ] 頁面上，選取要用於 [ **SSL 憑證**] 下拉式清單中的 [報表服務] 的憑證，**然後按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="41160-120">On the **Web Service URL** page, select the certificate to be used for your Reporting Services from the **SSL Certificate** dropdown list and then click **Apply**.</span></span> <span data-ttu-id="41160-121">幾秒鐘之後，您會在 [**報表伺服器 Web 服務 url**] 底下看到一組 url。</span><span class="sxs-lookup"><span data-stu-id="41160-121">After a few seconds, you will see a pair of URLs listed under **Report Server Web Service URLs**.</span></span>

5.  <span data-ttu-id="41160-122">按一下兩個 Url，確認您可以存取 SQL Server Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="41160-122">Click both of the URLs to verify that you can access SQL Server Reporting Services.</span></span>

6.  <span data-ttu-id="41160-123">關閉 Reporting Services 建構管理員。</span><span class="sxs-lookup"><span data-stu-id="41160-123">Close Reporting Services Configuration Manager.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="41160-124">建立與 SQL Server 2008 R2 搭配使用的 System Center Operations Manager 資料庫</span><span class="sxs-lookup"><span data-stu-id="41160-124">Creating a System Center Operations Manager database for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="41160-125">如果您想要將 System Center Operations Manager 設定為使用 SQL Server 2008 R2 資料庫，您必須在執行 SQL Server 2008 R2 的電腦上，「手動」建立 Operations Manager 資料庫。</span><span class="sxs-lookup"><span data-stu-id="41160-125">If you want to configure System Center Operations Manager to use a SQL Server 2008 R2 database, you will need to "manually" create the Operations Manager database on the computer running SQL Server 2008 R2.</span></span> <span data-ttu-id="41160-126">（同樣地，如果您是使用 SQL Server 2005 或 SQL Server 2008 做為後端資料庫，則不需要這些步驟。）</span><span class="sxs-lookup"><span data-stu-id="41160-126">(Again, these steps are not required if you are using SQL Server 2005 or SQL Server 2008 as your back-end database.)</span></span>

<span data-ttu-id="41160-127">若要手動建立 Operations Manager 資料庫，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="41160-127">To manually create an Operations Manager database do the following:</span></span>

1.  <span data-ttu-id="41160-128">在 System Center Operations Manager 2007 R2 設定媒體的 [SupportTools\\AMD64] 資料夾中，按兩下 [ **DBCreateWizard**]。</span><span class="sxs-lookup"><span data-stu-id="41160-128">On the System Center Operations Manager 2007 R2 setup media, in the SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="41160-129">在資料庫設定精靈中，按一下 [**歡迎使用資料庫設定向導]** 頁面上的 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-129">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="41160-130">在 [**資料庫資訊**] 頁面上，將所有設定保留原樣，然後按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="41160-130">On the **Database Information** page leave all the settings as-is and then click **Next**</span></span>

4.  <span data-ttu-id="41160-131">在 [**管理群組**設定] 頁面上，在 [**管理群組名稱**] 方塊中輸入管理群組的名稱（例如 [ **Lync Server Monitoring**）]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-131">On the **Management Group Configuration** page type a name for your Management Group (for example, **Lync Server Monitoring**) in the **Management Group name** box and then click **Next**.</span></span>

5.  <span data-ttu-id="41160-132">在 [ **Operations Manager 錯誤報表**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-132">On the **Operations Manager Error Reports** page click **Next**.</span></span>

6.  <span data-ttu-id="41160-133">按一下 [**摘要**] 頁面上的 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="41160-133">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="41160-134">建立與 SQL Server 2008 R2 搭配使用的 System Center Operations Manager 資料倉儲</span><span class="sxs-lookup"><span data-stu-id="41160-134">Creating a System Center Operations Manager data warehouse for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="41160-135">Microsoft Lync Server 2013 隨附三個新的系統中心作業管理員報告：</span><span class="sxs-lookup"><span data-stu-id="41160-135">Microsoft Lync Server 2013 ships with three new System Center Operations Manager reports:</span></span>

  - <span data-ttu-id="41160-136">**端對端案例可用性報告**   此報告詳細說明主要 Lync 伺服器服務（例如註冊或目前狀態）的可用性/正常運作時間。</span><span class="sxs-lookup"><span data-stu-id="41160-136">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="41160-137">**容量報告**   使用效能計數器資訊，此報告會顯示系統元件（例如記憶體可用性與處理器使用量）的趨勢。</span><span class="sxs-lookup"><span data-stu-id="41160-137">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="41160-138">**元件報告**   ：此報告會列出依 Lync Server 元件分組的上方警示發生器。</span><span class="sxs-lookup"><span data-stu-id="41160-138">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="41160-139">若要使用這些新的報表，您必須安裝 System Center Operations Manager 資料倉儲。</span><span class="sxs-lookup"><span data-stu-id="41160-139">In order to use these new reports you must install a System Center Operations Manager data warehouse.</span></span> <span data-ttu-id="41160-140">（資料倉儲提供對運營資料進行長期儲存）。若要將資料倉儲與 SQL Server 2008 R2 搭配使用，您必須在託管 SQL Server 資料庫的電腦上執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="41160-140">(A data warehouse provides for long-term storage of operations data.) To use a data warehouse with SQL Server 2008 R2 you must carry out the following steps on the computer that hosts your SQL Server database:</span></span>

1.  <span data-ttu-id="41160-141">在 System Center Operations Manager 安裝程式媒體上，在 [\\setup\\SupportTools AMD64] 資料夾中，按兩下 [ **DBCreateWizard**]。</span><span class="sxs-lookup"><span data-stu-id="41160-141">On the System Center Operations Manager setup media, in the Setup\\SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="41160-142">在資料庫設定精靈中，按一下 [**歡迎使用資料庫設定向導]** 頁面上的 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-142">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="41160-143">在 [**資料庫資訊**] 頁面上，從 [**資料庫類型**] 下拉式清單中選取 [ **Operations Manager 資料倉儲資料庫**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-143">On the **Database Information** page, select **Operations Manager Data Warehouse Database** from the **Database Type** dropdown list and then click **Next**.</span></span>

4.  <span data-ttu-id="41160-144">按一下 [**摘要**] 頁面上的 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="41160-144">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a><span data-ttu-id="41160-145">安裝 System Center Operations Manager 主控台</span><span class="sxs-lookup"><span data-stu-id="41160-145">Installing the System Center Operations Manager console</span></span>

<span data-ttu-id="41160-146">Operations Manager 主控台是用來管理 System Center Operations Manager 的主要工具。</span><span class="sxs-lookup"><span data-stu-id="41160-146">The Operations Manager console is the primary tool used to manage System Center Operations Manager.</span></span> <span data-ttu-id="41160-147">在安裝 Operations Manager 主控台之前，請確認您已安裝受支援的 SQL Server 版本及 SQL Server Reporting Service。</span><span class="sxs-lookup"><span data-stu-id="41160-147">Before you install the Operations Manager console, make sure that you have installed a supported version of SQL Server along with the SQL Server Reporting Service.</span></span> <span data-ttu-id="41160-148">此外，建議您執行 SQL Server 的 Reporting Services Configuration Manager，確認已正確安裝及設定報表服務。</span><span class="sxs-lookup"><span data-stu-id="41160-148">It is also recommended that you run SQL Server's Reporting Services Configuration Manager to verify that the Reporting Service has been correctly installed and configured.</span></span>

<span data-ttu-id="41160-149">若要安裝 System Center Operations Manager 主控台：</span><span class="sxs-lookup"><span data-stu-id="41160-149">To install the System Center Operations Manager console:</span></span>

1.  <span data-ttu-id="41160-150">在 System Center Operations Manager 安裝程式媒體上，按兩下 [ **SetupOM**]。</span><span class="sxs-lookup"><span data-stu-id="41160-150">On the System Center Operations Manager setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="41160-151">在 System Center Operations Manager 2007 R2 設定中，按一下 [**檢查必備元件**]。</span><span class="sxs-lookup"><span data-stu-id="41160-151">In System Center Operations Manager 2007 R2 Setup, click **Check Prerequisites**.</span></span>

3.  <span data-ttu-id="41160-152">在系統中心作業管理員必備檢視器中，選取要安裝的 System Center 元件：（**伺服器**;**主控台**;和**PowerShell**），然後按一下 [**檢查**]。</span><span class="sxs-lookup"><span data-stu-id="41160-152">In the System Center Operations Manager Prerequisite Viewer, select the System Center components to be installed: (**Server**; **Console**; and **PowerShell**) and then click **Check**.</span></span> <span data-ttu-id="41160-153">確認沒有報告任何封鎖問題，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="41160-153">Verify that no blocking issues have been reported and then click **Close**.</span></span> <span data-ttu-id="41160-154">如果已報告封鎖問題，請修正問題，然後按一下 [**檢查**] 以重新執行必要的測試。</span><span class="sxs-lookup"><span data-stu-id="41160-154">If a blocking issue has been reported, correct the problem and then click **Check** to re-run the prerequisite testing.</span></span>

4.  <span data-ttu-id="41160-155">在 System Center Operations Manager 安裝程式中，按一下 [**安裝 Operations Manager**]。</span><span class="sxs-lookup"><span data-stu-id="41160-155">In System Center Operations Manager Setup, click **Install Operations Manager**.</span></span>

5.  <span data-ttu-id="41160-156">在 System Center Operations Manager 安裝程式嚮導中，按一下 [**歡迎使用 System Center Operations Manager 安裝程式嚮導]** 頁面上的 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-156">In the System Center Operations Manager Setup wizard, on the **Welcome to the System Center Operations Manager Setup Wizard** page, click **Next**.</span></span>

6.  <span data-ttu-id="41160-157">在 [**使用者授權合約**] 頁面上，選取 **[我接受授權協定中的條款**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-157">On the **End-User License Agreement** page, select **I accept the terms in the license agreement** and then click **Next**.</span></span>

7.  <span data-ttu-id="41160-158">在 [**產品註冊**] 頁面上，于 [**使用者名稱**] 方塊中輸入您的名稱，並在 [**組織**] 方塊中輸入您組織的名稱。</span><span class="sxs-lookup"><span data-stu-id="41160-158">On the **Product Registration** page, type your name in the **User Name** box and name of your organization in the **Organization** box.</span></span> <span data-ttu-id="41160-159">在 [**輸入25位數的 CD 金鑰**] 方塊中，輸入 System Center Operations Manager 產品金鑰，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-159">Type your System Center Operations Manager product key in the **Enter your 25 digit CD Key** box and then click **Next**.</span></span>

8.  <span data-ttu-id="41160-160">在 [**自訂設定**] 頁面上，選取要安裝的 System Center 選項，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-160">On the **Custom Setup** page select the System Center options to be installed and then click **Next**.</span></span> <span data-ttu-id="41160-161">您應該選取 [**管理伺服器**]、[**使用者介面**] 和 [ **Web 主控台**] 進行安裝。</span><span class="sxs-lookup"><span data-stu-id="41160-161">You should select **Management Server**, **User Interfaces**, and **Web Console** to be installed.</span></span> <span data-ttu-id="41160-162">不應選取**資料庫**，也不應該安裝。</span><span class="sxs-lookup"><span data-stu-id="41160-162">**Database** should not be selected and should not be installed.</span></span>

9.  <span data-ttu-id="41160-163">在 [ **SC Database Server 實例**] 頁面上，確認安裝 Operations Manager 資料庫的電腦名稱稱出現在 [ **System Center database Server] （系統中心資料庫伺服器**）方塊中。</span><span class="sxs-lookup"><span data-stu-id="41160-163">On the **SC Database Server Instance** page, verify that the name of the computer where the Operations Manager databases are installed appears in the **System Center Database Server** box.</span></span> <span data-ttu-id="41160-164">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-164">Click **Next**.</span></span>

10. <span data-ttu-id="41160-165">在 [**管理伺服器動作帳戶**] 頁面上，選取 [**網域或本機電腦帳戶**]，然後在 [**使用者帳戶**]、[**密碼**] 和 [**網域] 或 [本機電腦**] 方塊中輸入適當的值。</span><span class="sxs-lookup"><span data-stu-id="41160-165">On the **Management Server Action Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="41160-166">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-166">Click **Next**.</span></span>

11. <span data-ttu-id="41160-167">在 [ **SDK 與 Config 服務帳戶**] 頁面上，選取 [**網域或本機電腦帳戶**]，然後在 [**使用者帳戶**]、[**密碼**] 和 [**網域] 或 [本機電腦**] 方塊中輸入適當的值。</span><span class="sxs-lookup"><span data-stu-id="41160-167">On the **SDK and Config Service Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="41160-168">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-168">Click **Next**.</span></span>

12. <span data-ttu-id="41160-169">在 [ **Operations Manager 錯誤報表**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-169">On the **Operations Manager Error Reports** page click **Next**.</span></span>

13. <span data-ttu-id="41160-170">在 [**客戶經驗改進計畫**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-170">On the **Customer Experience Improvement Program** page click **Next**.</span></span>

14. <span data-ttu-id="41160-171">在 [**準備好安裝程式**] 頁面上，按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="41160-171">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="41160-172">在 [**完成 System Center Operations Manager 設定**] 頁面上，清除 [**備份加密金鑰**]，然後**啟動 [主控台] 核取方塊**，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="41160-172">On the **Completing the System Center Operations Manager Setup** page, clear the **Backup Encryption Key** and **Start the console checkboxes** and then click **Finish**.</span></span>

16. <span data-ttu-id="41160-173">在 System Center Operations Manager 安裝程式中 **，按一下 [** 結束]。</span><span class="sxs-lookup"><span data-stu-id="41160-173">In System Center Operations Manager Setup click **Exit**.</span></span>

</div>

<div>

## <a name="installing-system-center-reporting-services"></a><span data-ttu-id="41160-174">安裝 System Center Reporting Services</span><span class="sxs-lookup"><span data-stu-id="41160-174">Installing System Center Reporting Services</span></span>

<span data-ttu-id="41160-175">安裝並設定 System Center Operations Manager 主控台之後，您必須安裝 System Center Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="41160-175">After installing and configuring the System Center Operations Manager console you must then install System Center Reporting Services.</span></span> <span data-ttu-id="41160-176">如果您使用的是 SQL Server 2008 R2 作為 Operations Manager 後端資料庫，這表示您必須先對與 SQL Server Reporting Services 相關聯的安全性群組進行暫時的變更。</span><span class="sxs-lookup"><span data-stu-id="41160-176">If you are using SQL Server 2008 R2 as your Operations Manager back-end database, that means that you must first make a temporary change to the security group associated with SQL Server Reporting Services.</span></span> <span data-ttu-id="41160-177">如果您使用的是 SQL Server 2008 R2，您必須執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="41160-177">If you are using SQL Server 2008 R2, you must do the following:</span></span>

1.  <span data-ttu-id="41160-178">按一下 [**開始**]，指向 [系統**管理工具**]，然後按一下 [**伺服器管理員**]。</span><span class="sxs-lookup"><span data-stu-id="41160-178">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="41160-179">在 [伺服器管理員] 中，展開 [設定] **，展開 [\*\*\*\*本機使用者和群組**]，然後按一下 [**群組**]。</span><span class="sxs-lookup"><span data-stu-id="41160-179">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="41160-180">找出下列群組，其中 atl sc-001 代表您電腦的名稱，而 ARCHINST 代表 System Center 資料庫的 SQL Server 實例： **SQLServerReportServerUser $ atl-sc-001 $ MSRS10\_50. ARCHINST**。</span><span class="sxs-lookup"><span data-stu-id="41160-180">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the System Center database: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

4.  <span data-ttu-id="41160-181">以滑鼠右鍵按一下群組，然後按一下 [**重新命名**]。</span><span class="sxs-lookup"><span data-stu-id="41160-181">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="41160-182">從組名中刪除\*\* \_50\*\* ，以重新命名群組。</span><span class="sxs-lookup"><span data-stu-id="41160-182">Rename the group by deleting **\_50** from the group name.</span></span> <span data-ttu-id="41160-183">例如： **SQLServerReportServerUser $ atl-sc-001 $ MSRS10。ARCHINST**。</span><span class="sxs-lookup"><span data-stu-id="41160-183">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

5.  <span data-ttu-id="41160-184">關閉 [伺服器管理員]。</span><span class="sxs-lookup"><span data-stu-id="41160-184">Close Server Manager.</span></span>

<span data-ttu-id="41160-185">此時，您就可以開始安裝 System Center 報表服務了。</span><span class="sxs-lookup"><span data-stu-id="41160-185">At this point you are ready to install System Center Reporting Services.</span></span> <span data-ttu-id="41160-186">若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="41160-186">To do this:</span></span>

1.  <span data-ttu-id="41160-187">在 System Center Operations Manager 2007 R2 設定媒體上，按兩下 [ **SetupOM**]。</span><span class="sxs-lookup"><span data-stu-id="41160-187">On the System Center Operations Manager 2007 R2 Setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="41160-188">在 System Center Operations Manager 2007 R2 設定中，按一下 [**安裝 Operations Manager 報告**]。</span><span class="sxs-lookup"><span data-stu-id="41160-188">In System Center Operations Manager 2007 R2 Setup, click **Install Operations Manager Reporting**.</span></span>

3.  <span data-ttu-id="41160-189">在系統中心作業管理器 2007 R2 報告設定向導中，按一下 [**歡迎使用 Operations Manager 報告設定**] 頁面上的 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-189">In the System Center Operations Manager 2007 R2 Reporting Setup wizard, on the **Welcome to Operations Manager Reporting Setup** page, click **Next**.</span></span>

4.  <span data-ttu-id="41160-190">在 [**使用者授權合約**] 頁面上，選取 **[我接受授權合約的條款**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-190">On the **End-user License Agreement** page select **I accept the terms of the license agreement** and then click **Next**.</span></span>

5.  <span data-ttu-id="41160-191">在 [**產品註冊**] 頁面上，確認您的名稱和組織名稱會出現在 [**使用者名稱**] 和 [**組織**] 方塊中，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-191">On the **Product Registration** page, ensure that your name and the name of your organization appear in the **User Name** and **Organization** boxes and then click **Next**.</span></span>

6.  <span data-ttu-id="41160-192">在 [**自訂設定**] 頁面上，按一下 [**報表伺服器**]，然後選取 [**此元件及所有相依元件]，將會安裝在本機磁片磁碟機上**。</span><span class="sxs-lookup"><span data-stu-id="41160-192">On the **Custom Setup** page, click **Reporting Server** and select **This component, and all dependent components, will be installed on local disk drive**.</span></span> <span data-ttu-id="41160-193">按一下 [**資料倉儲**]，然後選取 [**此元件將無法使用**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-193">Click **Data Warehouse** and select **This component will not be available**, and then click **Next**.</span></span>

7.  <span data-ttu-id="41160-194">在 [連線**至根目錄管理服務器]** 頁面上，于 [**根管理伺服器**] 方塊中輸入 Operations Manager 根管理伺服器的名稱，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-194">On the **Connect to the Root Management Server** page, type the name of your Operations Manager root management server in the **Root Management Server** box and then click **Next**.</span></span>

8.  <span data-ttu-id="41160-195">在 [連線**至 Operations Manager 資料倉儲]** 頁面上，輸入您的資料倉儲位於 [ **Sql server 實例**] 方塊中的 sql server 實例。</span><span class="sxs-lookup"><span data-stu-id="41160-195">On the **Connect to the Operations Manager Data Warehouse** page, type the SQL Server instance where your data warehouse is located in the **SQL Server Instance** box.</span></span> <span data-ttu-id="41160-196">（如果您的資料倉儲位於預設實例中，請只需輸入伺服器名稱; 例如： atl-sql-001）。確認 [**名稱**] 方塊中出現 [資料庫名稱**OperationsManagerDW** ]，且 [ **SQL Server 埠**] 方塊中出現 [埠**1433** ]。</span><span class="sxs-lookup"><span data-stu-id="41160-196">(If your data warehouse is located in the Default instance then simply type the server name; for example: atl-sql-001.) Verify that the database name **OperationsManagerDW** appears in the **Name** box, and that port **1433** appears in the **SQL Server port** box.</span></span> <span data-ttu-id="41160-197">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-197">Click **Next**.</span></span>

9.  <span data-ttu-id="41160-198">在 [ **SQL Server 報表實例**] 頁面上，從 [**輸入 Sql Server reporting Services 伺服器**] 下拉式清單中選取您的 sql server 報表伺服器，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-198">On the **SQL Server Reporting Instance** page, select your SQL Server reporting server from the **Enter the SQL Server Reporting Services Server** dropdown list and then click **Next**.</span></span>

10. <span data-ttu-id="41160-199">在 [**資料倉儲寫入帳戶**] 頁面上，于 [**使用者帳戶**] 和 [**密碼**] 方塊中，輸入要為其初始指派寫入權限的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="41160-199">On the **Data Warehouse Write Account** page, enter the name and password of the user to be initially assigned write permissions to the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="41160-200">從 [**網域**] 下拉式清單中選取使用者的網域，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-200">Select the user's domain from the **Domain** dropdown list and then click **Next**.</span></span>

11. <span data-ttu-id="41160-201">在 [**資料讀取器帳戶**] 頁面上，輸入要在 SQL Reporting Services 查詢 [**使用者帳戶**] 和 [**密碼**] 方塊中的資料倉儲時所要使用的使用者帳戶名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="41160-201">On the **Data Reader Account** page, enter the name and password of the user account to be used when SQL Reporting Services queries the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="41160-202">從 [**網域**] 下拉式清單中選取 [帳戶網域]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-202">Select the account domain from the **Domain** dropdown list and then click **Next**.</span></span>

12. <span data-ttu-id="41160-203">在 [**運算元據報表**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-203">On the **Operational Data Reports** page, click **Next**.</span></span>

13. <span data-ttu-id="41160-204">在 [ **Microsoft Update** ] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="41160-204">On the **Microsoft Update** page, click **Next**.</span></span>

14. <span data-ttu-id="41160-205">在 [**準備好安裝程式**] 頁面上，按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="41160-205">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="41160-206">在 [**完成 Operations Manager 報告元件安裝程式嚮導]** 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="41160-206">On the **Completing the Operations Manager Reporting Components Setup Wizard** page, click **Finish**.</span></span>

16. <span data-ttu-id="41160-207">在 System Center Operations Manager 2007 R2 設定中，**按一下 [** 結束]。</span><span class="sxs-lookup"><span data-stu-id="41160-207">In System Center Operations Manager 2007 R2 Setup, click **Exit**.</span></span>

<span data-ttu-id="41160-208">安裝 System Center 報表之後，您可以使用下列程式來重設與 SQL Server 報告相關聯之安全性群組的名稱。</span><span class="sxs-lookup"><span data-stu-id="41160-208">After System Center reporting has been installed you then use the following procedure to reset the name of the security group associated with SQL Server reporting.</span></span> <span data-ttu-id="41160-209">同樣地，只有在您使用 SQL Server 時，才需要執行此程式：</span><span class="sxs-lookup"><span data-stu-id="41160-209">Again, this procedure is only required if you are using SQL Server:</span></span>

1.  <span data-ttu-id="41160-210">按一下 [**開始**]，指向 [系統**管理工具**]，然後按一下 [**伺服器管理員**]。</span><span class="sxs-lookup"><span data-stu-id="41160-210">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="41160-211">在 [伺服器管理員] 中，展開 [設定] **，展開 [\*\*\*\*本機使用者和群組**]，然後按一下 [**群組**]。</span><span class="sxs-lookup"><span data-stu-id="41160-211">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="41160-212">找出下列群組，其中 atl sc-001 代表您電腦的名稱，而 ARCHINST 代表封存與監控資料庫的 SQL Server 實例： **SQLServerReportServerUser $ atl-sc-001 $ MSRS10。ARCHINST**。</span><span class="sxs-lookup"><span data-stu-id="41160-212">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the archiving and monitoring databases: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

4.  <span data-ttu-id="41160-213">以滑鼠右鍵按一下群組，然後按一下 [**重新命名**]。</span><span class="sxs-lookup"><span data-stu-id="41160-213">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="41160-214">將\*\* \_50\*\*新增至組名的結尾，在 SQL Server 實例名稱前面加上，即可重新命名群組。</span><span class="sxs-lookup"><span data-stu-id="41160-214">Rename the group by adding **\_50** to the end of the group name, right before the SQL Server instance name.</span></span> <span data-ttu-id="41160-215">例如： **SQLServerReportServerUser $ atl-sc-001 $ MSRS10\_50. ARCHINST**。</span><span class="sxs-lookup"><span data-stu-id="41160-215">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

5.  <span data-ttu-id="41160-216">關閉 [伺服器管理員]。</span><span class="sxs-lookup"><span data-stu-id="41160-216">Close Server Manager.</span></span>

<span data-ttu-id="41160-217">如果 System Center 操作主控台已開啟，您將需要關閉該應用程式，然後重新開機它;如果您不這麼做，[**報告**] 索引標籤就不會出現在 [操作] 主控台使用者介面中。</span><span class="sxs-lookup"><span data-stu-id="41160-217">If the System Center Operations Console is open you will need to close the application and then restart it; if you do not do this the **Reporting** tab will not appear in the Operations Console user interface.</span></span> <span data-ttu-id="41160-218">請注意，第一次重新開機作業主控台之後，可能需要幾分鐘的時間，所有的監視報告才會出現在 [**報告**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="41160-218">Note that, after restarting the Operations Console the first time, it could take several minutes before all the Monitoring Reports appear on the **Reporting** tab.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

