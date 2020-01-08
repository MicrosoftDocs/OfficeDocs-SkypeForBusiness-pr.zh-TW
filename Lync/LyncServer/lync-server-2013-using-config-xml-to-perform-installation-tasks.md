---
title: Lync Server 2013：使用 Config.xml 執行安裝任務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Config.xml to perform installation tasks
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204651(v=OCS.15)
ms:contentKeyID: 48183332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3fb6f4c77375781b6c5d767087ad61f3ec6401b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a><span data-ttu-id="12601-102">使用 Config.xml 在 Lync Server 2013 中執行安裝工作</span><span class="sxs-lookup"><span data-stu-id="12601-102">Using Config.xml to perform installation tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12601-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="12601-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="12601-104">雖然 Office 自訂工具（OCT）是自訂安裝的主要工具，但系統管理員可以使用 Config.xml 檔案來指定不在 OCT 中提供的其他安裝指示。</span><span class="sxs-lookup"><span data-stu-id="12601-104">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT.</span></span> <span data-ttu-id="12601-105">下列自訂功能只能使用 Config.xml 檔案來進行：</span><span class="sxs-lookup"><span data-stu-id="12601-105">The following customizations can only be made by using the Config.xml file:</span></span>

  - <span data-ttu-id="12601-106">指定網路安裝點的路徑。</span><span class="sxs-lookup"><span data-stu-id="12601-106">Specify the path of the network installation point.</span></span>

  - <span data-ttu-id="12601-107">選取要安裝的產品。</span><span class="sxs-lookup"><span data-stu-id="12601-107">Select the products to install.</span></span>

  - <span data-ttu-id="12601-108">設定記錄，以及安裝程式自訂檔案和軟體更新的位置。</span><span class="sxs-lookup"><span data-stu-id="12601-108">Configure logging and the location of the Setup customization file and software updates.</span></span>

  - <span data-ttu-id="12601-109">指定安裝選項，例如 [使用者名稱]。</span><span class="sxs-lookup"><span data-stu-id="12601-109">Specify installation options, such as user name.</span></span>

  - <span data-ttu-id="12601-110">將本機安裝來源（.LIS）複製到使用者的電腦，但不安裝 Office。</span><span class="sxs-lookup"><span data-stu-id="12601-110">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

  - <span data-ttu-id="12601-111">新增或移除安裝的語言。</span><span class="sxs-lookup"><span data-stu-id="12601-111">Add or remove languages from the installation.</span></span>

<span data-ttu-id="12601-112">建議您使用 Config.xml 檔案來設定 Lync 2013 無訊息安裝。</span><span class="sxs-lookup"><span data-stu-id="12601-112">We recommend that you use the Config.xml file to configure Lync 2013 silent installation.</span></span>

<span data-ttu-id="12601-113">根據預設，儲存在核心產品資料夾中的 Config.xml 檔案（例如 [產品]） \\。WW）指示安裝程式安裝該產品。</span><span class="sxs-lookup"><span data-stu-id="12601-113">By default, the Config.xml file that is stored in the core product folder (for example, \\product.WW) directs Setup to install that product.</span></span> <span data-ttu-id="12601-114">例如，下列資料夾中的 Config.xml 檔案會安裝 Lync 2013：</span><span class="sxs-lookup"><span data-stu-id="12601-114">For example, the Config.xml file in the following folder installs Lync 2013:</span></span>

  - <span data-ttu-id="12601-115">\\\\伺服器\\共用\\Lync15\\Lync WW \\.xml</span><span class="sxs-lookup"><span data-stu-id="12601-115">\\\\server\\share\\Lync15\\Lync.WW \\Config.xml</span></span>

<span data-ttu-id="12601-116">下表列出最常用於 Lync 2013 安裝的 Config.xml 元素。</span><span class="sxs-lookup"><span data-stu-id="12601-116">The Config.xml elements most commonly used for Lync 2013 installation are listed in the following table.</span></span>

### <a name="configxml-elements"></a><span data-ttu-id="12601-117">Config .xml 元素</span><span class="sxs-lookup"><span data-stu-id="12601-117">Config.xml elements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12601-118">元件</span><span class="sxs-lookup"><span data-stu-id="12601-118">Element</span></span></th>
<th><span data-ttu-id="12601-119">描述</span><span class="sxs-lookup"><span data-stu-id="12601-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12601-120">Configuration</span><span class="sxs-lookup"><span data-stu-id="12601-120">Configuration</span></span></p></td>
<td><p><span data-ttu-id="12601-121">高層元素（必要）。</span><span class="sxs-lookup"><span data-stu-id="12601-121">Top-level element (required).</span></span> <span data-ttu-id="12601-122">包含 Product 屬性，例如： Product = Lync</span><span class="sxs-lookup"><span data-stu-id="12601-122">Contains the Product attribute, for example: Product=Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12601-123">OptionState</span><span class="sxs-lookup"><span data-stu-id="12601-123">OptionState</span></span></p></td>
<td><p><span data-ttu-id="12601-124">指定安裝期間特定產品功能的處理方式。</span><span class="sxs-lookup"><span data-stu-id="12601-124">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="12601-125">使用下列屬性來避免安裝 Business Connectivity Service，包括干擾 Outlook 2010 的共用元件：</span><span class="sxs-lookup"><span data-stu-id="12601-125">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook 2010:</span></span></p>
<ul>
<li><p><span data-ttu-id="12601-126">識別碼 =&quot;LOBiMain&quot;</span><span class="sxs-lookup"><span data-stu-id="12601-126">Id=&quot;LOBiMain&quot;</span></span></p></li>
<li><p><span data-ttu-id="12601-127">State =&quot;不存在&quot;</span><span class="sxs-lookup"><span data-stu-id="12601-127">State=&quot;Absent&quot;</span></span></p></li>
<li><p><span data-ttu-id="12601-128">子級 =&quot;Force&quot;</span><span class="sxs-lookup"><span data-stu-id="12601-128">Children=&quot;Force&quot;</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12601-129">顯示幕</span><span class="sxs-lookup"><span data-stu-id="12601-129">Display</span></span></p></td>
<td><p><span data-ttu-id="12601-130">安裝程式顯示給使用者的 UI 層級。</span><span class="sxs-lookup"><span data-stu-id="12601-130">The level of UI that Setup displays to the user.</span></span> <span data-ttu-id="12601-131">一般屬性包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="12601-131">Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="12601-132">CompletionNotice =&quot;是&quot; | &quot;否&quot;（預設值）</span><span class="sxs-lookup"><span data-stu-id="12601-132">CompletionNotice=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
<li><p><span data-ttu-id="12601-133">AcceptEula =&quot;是&quot; | &quot;否&quot;（預設值）</span><span class="sxs-lookup"><span data-stu-id="12601-133">AcceptEula=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12601-134">記錄</span><span class="sxs-lookup"><span data-stu-id="12601-134">Logging</span></span></p></td>
<td><p><span data-ttu-id="12601-135">安裝程式所執行之記錄類型的選項。</span><span class="sxs-lookup"><span data-stu-id="12601-135">Options for the kind of logging that Setup performs.</span></span> <span data-ttu-id="12601-136">一般屬性包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="12601-136">Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="12601-137">輸入 =&quot;Off&quot; | &quot;標準&quot;（預設值） |&quot;詳細資訊&quot;</span><span class="sxs-lookup"><span data-stu-id="12601-137">Type =&quot;Off&quot; | &quot;Standard&quot;(default) | &quot;Verbose&quot;</span></span></p></li>
<li><p><span data-ttu-id="12601-138">Template = "filename .txt" （記錄檔的名稱）</span><span class="sxs-lookup"><span data-stu-id="12601-138">Template=”filename.txt” (the name of the log file)</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12601-139">正在</span><span class="sxs-lookup"><span data-stu-id="12601-139">Setting</span></span></p></td>
<td><p><span data-ttu-id="12601-140">指定 Windows 安裝程式屬性的值。</span><span class="sxs-lookup"><span data-stu-id="12601-140">Specifies values for Windows Installer properties.</span></span> <span data-ttu-id="12601-141">一般屬性包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="12601-141">Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="12601-142">設定識別碼 =&quot;Name&quot; （Windows Installer 屬性的名稱）</span><span class="sxs-lookup"><span data-stu-id="12601-142">Setting Id=&quot;name&quot; (the name of the Windows Installer property)</span></span></p></li>
<li><p><span data-ttu-id="12601-143">值 =&quot;value&quot; （要指派給屬性的值）</span><span class="sxs-lookup"><span data-stu-id="12601-143">Value=&quot;value&quot; (the value to assign to the property)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12601-144">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="12601-144">DistributionPoint</span></span></p></td>
<td><p><span data-ttu-id="12601-145">要執行安裝的網路安裝點的完整路徑。</span><span class="sxs-lookup"><span data-stu-id="12601-145">The fully qualified path of the network installation point from which the installation is to run.</span></span> <span data-ttu-id="12601-146">包括 Location 屬性：</span><span class="sxs-lookup"><span data-stu-id="12601-146">Includes the Location attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="12601-147">位置 = "path"</span><span class="sxs-lookup"><span data-stu-id="12601-147">Location=”path”</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="12601-148">下列範例顯示 Lync 2013 典型無訊息安裝的 Config.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="12601-148">The following example shows a Config.xml file for a typical silent installation of Lync 2013.</span></span>

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

<span data-ttu-id="12601-149">有關使用 Config.xml 檔案來執行 Office 安裝與維護工作的詳細資訊，請參閱<http://go.microsoft.com/fwlink/p/?linkid=267514>。</span><span class="sxs-lookup"><span data-stu-id="12601-149">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at <http://go.microsoft.com/fwlink/p/?linkid=267514>.</span></span>

<div>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="12601-150">自訂 Config.xml 檔案</span><span class="sxs-lookup"><span data-stu-id="12601-150">To customize the Config.xml file</span></span>

1.  <span data-ttu-id="12601-151">使用文字編輯器工具（例如記事本）來開啟 Config.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="12601-151">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2.  <span data-ttu-id="12601-152">找出包含您要變更之元素的線條。</span><span class="sxs-lookup"><span data-stu-id="12601-152">Locate the lines that contain the elements you want to change.</span></span>

3.  <span data-ttu-id="12601-153">使用您要使用的緘默選項來修改元素專案。</span><span class="sxs-lookup"><span data-stu-id="12601-153">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="12601-154">請務必移除批註分隔符號 "\<\!--" 和 "--\>"。</span><span class="sxs-lookup"><span data-stu-id="12601-154">Make sure that you remove the comment delimiters, "\<\!--" and "--\>".</span></span> <span data-ttu-id="12601-155">例如，使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="12601-155">For example, use the following syntax:</span></span>
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  <span data-ttu-id="12601-156">儲存 Config.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="12601-156">Save the Config.xml file.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

