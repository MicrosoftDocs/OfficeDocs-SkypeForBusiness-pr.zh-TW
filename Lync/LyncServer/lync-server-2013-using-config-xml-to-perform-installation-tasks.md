---
title: Lync Server 2013：使用 Config.xml 執行安裝工作
description: Lync Server 2013：使用 Config.xml 執行安裝工作。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Config.xml to perform installation tasks
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204651(v=OCS.15)
ms:contentKeyID: 48183332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22fff14e21a120c3a0ee2cd6432fd1eba2bbee5f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580399"
---
# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a><span data-ttu-id="da116-103">在 Lync Server 2013 中使用 Config.xml 執行安裝工作</span><span class="sxs-lookup"><span data-stu-id="da116-103">Using Config.xml to perform installation tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da116-104">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="da116-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="da116-p101">雖然 Office 自訂工具 (OCT) 是自訂安裝的主要工具，但是系統管理員可以使用 Config.xml 檔案來指定 OCT 中所沒有的其他安裝指示。下列自訂只能使用 Config.xml 檔案來進行：</span><span class="sxs-lookup"><span data-stu-id="da116-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>

  - <span data-ttu-id="da116-107">指定網路安裝點的路徑。</span><span class="sxs-lookup"><span data-stu-id="da116-107">Specify the path of the network installation point.</span></span>

  - <span data-ttu-id="da116-108">選取所要安裝的產品。</span><span class="sxs-lookup"><span data-stu-id="da116-108">Select the products to install.</span></span>

  - <span data-ttu-id="da116-109">設定安裝程式自訂檔案和軟體更新的記錄及位置。</span><span class="sxs-lookup"><span data-stu-id="da116-109">Configure logging and the location of the Setup customization file and software updates.</span></span>

  - <span data-ttu-id="da116-110">指定安裝選項，例如使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="da116-110">Specify installation options, such as user name.</span></span>

  - <span data-ttu-id="da116-111">將本機安裝來源 (LIS) 複製到使用者的電腦，而不安裝 Office。</span><span class="sxs-lookup"><span data-stu-id="da116-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

  - <span data-ttu-id="da116-112">在安裝中新增或移除語言。</span><span class="sxs-lookup"><span data-stu-id="da116-112">Add or remove languages from the installation.</span></span>

<span data-ttu-id="da116-113">建議您使用 Config.xml 檔案來設定 Lync 2013 無訊息安裝。</span><span class="sxs-lookup"><span data-stu-id="da116-113">We recommend that you use the Config.xml file to configure Lync 2013 silent installation.</span></span>

<span data-ttu-id="da116-114">根據預設，在核心產品資料夾中儲存的 Config.xml 檔案 (例如 \\ product。WW) 指示安裝程式安裝該產品。</span><span class="sxs-lookup"><span data-stu-id="da116-114">By default, the Config.xml file that is stored in the core product folder (for example, \\product.WW) directs Setup to install that product.</span></span> <span data-ttu-id="da116-115">例如，下列資料夾中的 Config.xml 檔會安裝 Lync 2013：</span><span class="sxs-lookup"><span data-stu-id="da116-115">For example, the Config.xml file in the following folder installs Lync 2013:</span></span>

  - <span data-ttu-id="da116-116">\\\\伺服器 \\ 共用 \\ Lync15 \\ Lync \\Config.xml</span><span class="sxs-lookup"><span data-stu-id="da116-116">\\\\server\\share\\Lync15\\Lync.WW \\Config.xml</span></span>

<span data-ttu-id="da116-117">下表列出最常用於 Lync 2013 安裝的 Config.xml 元素。</span><span class="sxs-lookup"><span data-stu-id="da116-117">The Config.xml elements most commonly used for Lync 2013 installation are listed in the following table.</span></span>

### <a name="configxml-elements"></a><span data-ttu-id="da116-118">Config.xml 元素</span><span class="sxs-lookup"><span data-stu-id="da116-118">Config.xml elements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da116-119">元素</span><span class="sxs-lookup"><span data-stu-id="da116-119">Element</span></span></th>
<th><span data-ttu-id="da116-120">描述</span><span class="sxs-lookup"><span data-stu-id="da116-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da116-121">組態</span><span class="sxs-lookup"><span data-stu-id="da116-121">Configuration</span></span></p></td>
<td><p><span data-ttu-id="da116-p103">最上層元素 (必要)。包含 Product 屬性，例如：Product=Lync</span><span class="sxs-lookup"><span data-stu-id="da116-p103">Top-level element (required). Contains the Product attribute, for example: Product=Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da116-124">OptionState</span><span class="sxs-lookup"><span data-stu-id="da116-124">OptionState</span></span></p></td>
<td><p><span data-ttu-id="da116-125">指定在安裝期間如何處理特定的產品功能。</span><span class="sxs-lookup"><span data-stu-id="da116-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="da116-126">使用下列屬性可防止安裝 Business Connectivity Services，其中包含干擾 Outlook 2010 的共用元件：</span><span class="sxs-lookup"><span data-stu-id="da116-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook 2010:</span></span></p>
<ul>
<li><p><span data-ttu-id="da116-127">識別碼 = &quot; LOBiMain&quot;</span><span class="sxs-lookup"><span data-stu-id="da116-127">Id=&quot;LOBiMain&quot;</span></span></p></li>
<li><p><span data-ttu-id="da116-128">State = 不 &quot; 存在&quot;</span><span class="sxs-lookup"><span data-stu-id="da116-128">State=&quot;Absent&quot;</span></span></p></li>
<li><p><span data-ttu-id="da116-129">子系 = &quot; 強制&quot;</span><span class="sxs-lookup"><span data-stu-id="da116-129">Children=&quot;Force&quot;</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da116-130">顯示器</span><span class="sxs-lookup"><span data-stu-id="da116-130">Display</span></span></p></td>
<td><p><span data-ttu-id="da116-p105">安裝程式向使用者顯示的 UI 層級。一般屬性包括：</span><span class="sxs-lookup"><span data-stu-id="da116-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="da116-133">CompletionNotice= &quot; 是 &quot;  |  &quot; 否 &quot; (預設) </span><span class="sxs-lookup"><span data-stu-id="da116-133">CompletionNotice=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
<li><p><span data-ttu-id="da116-134">AcceptEula= &quot; 是 &quot;  |  &quot; 否 &quot; (預設) </span><span class="sxs-lookup"><span data-stu-id="da116-134">AcceptEula=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da116-135">記錄</span><span class="sxs-lookup"><span data-stu-id="da116-135">Logging</span></span></p></td>
<td><p><span data-ttu-id="da116-p106">安裝程式執行之記錄類型的選項。一般屬性包括：</span><span class="sxs-lookup"><span data-stu-id="da116-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="da116-138">Type = &quot; Off &quot;  |  &quot; Standard &quot; (default) | &quot;詳細&quot;</span><span class="sxs-lookup"><span data-stu-id="da116-138">Type =&quot;Off&quot; | &quot;Standard&quot;(default) | &quot;Verbose&quot;</span></span></p></li>
<li><p><span data-ttu-id="da116-139">Template=”檔案名稱.txt” (記錄檔名稱)</span><span class="sxs-lookup"><span data-stu-id="da116-139">Template=”filename.txt” (the name of the log file)</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da116-140">設定</span><span class="sxs-lookup"><span data-stu-id="da116-140">Setting</span></span></p></td>
<td><p><span data-ttu-id="da116-p107">指定 Windows Installer 內容的值。一般屬性包括：</span><span class="sxs-lookup"><span data-stu-id="da116-p107">Specifies values for Windows Installer properties. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="da116-143">設定識別碼 = &quot; name &quot; (Windows Installer 屬性的名稱) </span><span class="sxs-lookup"><span data-stu-id="da116-143">Setting Id=&quot;name&quot; (the name of the Windows Installer property)</span></span></p></li>
<li><p><span data-ttu-id="da116-144">Value = &quot; value &quot; (要指派給屬性的值) </span><span class="sxs-lookup"><span data-stu-id="da116-144">Value=&quot;value&quot; (the value to assign to the property)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da116-145">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="da116-145">DistributionPoint</span></span></p></td>
<td><p><span data-ttu-id="da116-p108">要執行安裝之網路安裝點的完整路徑。包括 Location 屬性：</span><span class="sxs-lookup"><span data-stu-id="da116-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="da116-148">Location = "path"</span><span class="sxs-lookup"><span data-stu-id="da116-148">Location=”path”</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="da116-149">下列範例顯示 Lync 2013 一般無訊息安裝的 Config.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="da116-149">The following example shows a Config.xml file for a typical silent installation of Lync 2013.</span></span>

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

<span data-ttu-id="da116-150">您可以在使用 Config.xml 檔案執行 Office 安裝及維護工作的詳細資訊 <https://go.microsoft.com/fwlink/p/?linkid=267514> 。</span><span class="sxs-lookup"><span data-stu-id="da116-150">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at <https://go.microsoft.com/fwlink/p/?linkid=267514>.</span></span>

<div>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="da116-151">自訂 Config.xml 檔案</span><span class="sxs-lookup"><span data-stu-id="da116-151">To customize the Config.xml file</span></span>

1.  <span data-ttu-id="da116-152">使用文字編輯器工具來開啟 Config.xml 檔案，例如 [記事本]。</span><span class="sxs-lookup"><span data-stu-id="da116-152">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2.  <span data-ttu-id="da116-153">找到包含您要變更之元素的那幾行。</span><span class="sxs-lookup"><span data-stu-id="da116-153">Locate the lines that contain the elements you want to change.</span></span>

3.  <span data-ttu-id="da116-154">以您要使用的無訊息選項來修改元素項目。</span><span class="sxs-lookup"><span data-stu-id="da116-154">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="da116-155">請務必移除批註定界符 " \<\!--" and "--\> "。</span><span class="sxs-lookup"><span data-stu-id="da116-155">Make sure that you remove the comment delimiters, "\<\!--" and "--\>".</span></span> <span data-ttu-id="da116-156">例如，使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="da116-156">For example, use the following syntax:</span></span>
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  <span data-ttu-id="da116-157">儲存 Config.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="da116-157">Save the Config.xml file.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

