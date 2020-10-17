---
title: Lync Server 2013：使用 Config.xml 執行安裝工作
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
ms.openlocfilehash: 901d95797955c6f545c0d305e2c855829c92addf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535780"
---
# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a><span data-ttu-id="e91fa-102">在 Lync Server 2013 中使用 Config.xml 執行安裝工作</span><span class="sxs-lookup"><span data-stu-id="e91fa-102">Using Config.xml to perform installation tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e91fa-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e91fa-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e91fa-p101">雖然 Office 自訂工具 (OCT) 是自訂安裝的主要工具，但是系統管理員可以使用 Config.xml 檔案來指定 OCT 中所沒有的其他安裝指示。下列自訂只能使用 Config.xml 檔案來進行：</span><span class="sxs-lookup"><span data-stu-id="e91fa-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>

  - <span data-ttu-id="e91fa-106">指定網路安裝點的路徑。</span><span class="sxs-lookup"><span data-stu-id="e91fa-106">Specify the path of the network installation point.</span></span>

  - <span data-ttu-id="e91fa-107">選取所要安裝的產品。</span><span class="sxs-lookup"><span data-stu-id="e91fa-107">Select the products to install.</span></span>

  - <span data-ttu-id="e91fa-108">設定安裝程式自訂檔案和軟體更新的記錄及位置。</span><span class="sxs-lookup"><span data-stu-id="e91fa-108">Configure logging and the location of the Setup customization file and software updates.</span></span>

  - <span data-ttu-id="e91fa-109">指定安裝選項，例如使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="e91fa-109">Specify installation options, such as user name.</span></span>

  - <span data-ttu-id="e91fa-110">將本機安裝來源 (LIS) 複製到使用者的電腦，而不安裝 Office。</span><span class="sxs-lookup"><span data-stu-id="e91fa-110">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

  - <span data-ttu-id="e91fa-111">在安裝中新增或移除語言。</span><span class="sxs-lookup"><span data-stu-id="e91fa-111">Add or remove languages from the installation.</span></span>

<span data-ttu-id="e91fa-112">建議您使用 Config.xml 檔案來設定 Lync 2013 無訊息安裝。</span><span class="sxs-lookup"><span data-stu-id="e91fa-112">We recommend that you use the Config.xml file to configure Lync 2013 silent installation.</span></span>

<span data-ttu-id="e91fa-113">根據預設，在核心產品資料夾中儲存的 Config.xml 檔案 (例如 \\ product。WW) 指示安裝程式安裝該產品。</span><span class="sxs-lookup"><span data-stu-id="e91fa-113">By default, the Config.xml file that is stored in the core product folder (for example, \\product.WW) directs Setup to install that product.</span></span> <span data-ttu-id="e91fa-114">例如，下列資料夾中的 Config.xml 檔會安裝 Lync 2013：</span><span class="sxs-lookup"><span data-stu-id="e91fa-114">For example, the Config.xml file in the following folder installs Lync 2013:</span></span>

  - <span data-ttu-id="e91fa-115">\\\\伺服器 \\ 共用 \\ Lync15 \\ Lync \\Config.xml</span><span class="sxs-lookup"><span data-stu-id="e91fa-115">\\\\server\\share\\Lync15\\Lync.WW \\Config.xml</span></span>

<span data-ttu-id="e91fa-116">下表列出最常用於 Lync 2013 安裝的 Config.xml 元素。</span><span class="sxs-lookup"><span data-stu-id="e91fa-116">The Config.xml elements most commonly used for Lync 2013 installation are listed in the following table.</span></span>

### <a name="configxml-elements"></a><span data-ttu-id="e91fa-117">Config.xml 元素</span><span class="sxs-lookup"><span data-stu-id="e91fa-117">Config.xml elements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e91fa-118">元素</span><span class="sxs-lookup"><span data-stu-id="e91fa-118">Element</span></span></th>
<th><span data-ttu-id="e91fa-119">描述</span><span class="sxs-lookup"><span data-stu-id="e91fa-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e91fa-120">組態</span><span class="sxs-lookup"><span data-stu-id="e91fa-120">Configuration</span></span></p></td>
<td><p><span data-ttu-id="e91fa-p103">最上層元素 (必要)。包含 Product 屬性，例如：Product=Lync</span><span class="sxs-lookup"><span data-stu-id="e91fa-p103">Top-level element (required). Contains the Product attribute, for example: Product=Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e91fa-123">OptionState</span><span class="sxs-lookup"><span data-stu-id="e91fa-123">OptionState</span></span></p></td>
<td><p><span data-ttu-id="e91fa-124">指定在安裝期間如何處理特定的產品功能。</span><span class="sxs-lookup"><span data-stu-id="e91fa-124">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="e91fa-125">使用下列屬性可防止安裝 Business Connectivity Services，其中包含干擾 Outlook 2010 的共用元件：</span><span class="sxs-lookup"><span data-stu-id="e91fa-125">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook 2010:</span></span></p>
<ul>
<li><p><span data-ttu-id="e91fa-126">識別碼 = &quot; LOBiMain&quot;</span><span class="sxs-lookup"><span data-stu-id="e91fa-126">Id=&quot;LOBiMain&quot;</span></span></p></li>
<li><p><span data-ttu-id="e91fa-127">State = 不 &quot; 存在&quot;</span><span class="sxs-lookup"><span data-stu-id="e91fa-127">State=&quot;Absent&quot;</span></span></p></li>
<li><p><span data-ttu-id="e91fa-128">子系 = &quot; 強制&quot;</span><span class="sxs-lookup"><span data-stu-id="e91fa-128">Children=&quot;Force&quot;</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e91fa-129">顯示器</span><span class="sxs-lookup"><span data-stu-id="e91fa-129">Display</span></span></p></td>
<td><p><span data-ttu-id="e91fa-p105">安裝程式向使用者顯示的 UI 層級。一般屬性包括：</span><span class="sxs-lookup"><span data-stu-id="e91fa-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e91fa-132">CompletionNotice= &quot; 是 &quot;  |  &quot; 否 &quot; (預設) </span><span class="sxs-lookup"><span data-stu-id="e91fa-132">CompletionNotice=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
<li><p><span data-ttu-id="e91fa-133">AcceptEula= &quot; 是 &quot;  |  &quot; 否 &quot; (預設) </span><span class="sxs-lookup"><span data-stu-id="e91fa-133">AcceptEula=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e91fa-134">記錄</span><span class="sxs-lookup"><span data-stu-id="e91fa-134">Logging</span></span></p></td>
<td><p><span data-ttu-id="e91fa-p106">安裝程式執行之記錄類型的選項。一般屬性包括：</span><span class="sxs-lookup"><span data-stu-id="e91fa-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e91fa-137">Type = &quot; Off &quot;  |  &quot; Standard &quot; (default) | &quot;詳細&quot;</span><span class="sxs-lookup"><span data-stu-id="e91fa-137">Type =&quot;Off&quot; | &quot;Standard&quot;(default) | &quot;Verbose&quot;</span></span></p></li>
<li><p><span data-ttu-id="e91fa-138">Template=”檔案名稱.txt” (記錄檔名稱)</span><span class="sxs-lookup"><span data-stu-id="e91fa-138">Template=”filename.txt” (the name of the log file)</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e91fa-139">設定</span><span class="sxs-lookup"><span data-stu-id="e91fa-139">Setting</span></span></p></td>
<td><p><span data-ttu-id="e91fa-p107">指定 Windows Installer 內容的值。一般屬性包括：</span><span class="sxs-lookup"><span data-stu-id="e91fa-p107">Specifies values for Windows Installer properties. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e91fa-142">設定識別碼 = &quot; name &quot; (Windows Installer 屬性的名稱) </span><span class="sxs-lookup"><span data-stu-id="e91fa-142">Setting Id=&quot;name&quot; (the name of the Windows Installer property)</span></span></p></li>
<li><p><span data-ttu-id="e91fa-143">Value = &quot; value &quot; (要指派給屬性的值) </span><span class="sxs-lookup"><span data-stu-id="e91fa-143">Value=&quot;value&quot; (the value to assign to the property)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e91fa-144">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="e91fa-144">DistributionPoint</span></span></p></td>
<td><p><span data-ttu-id="e91fa-p108">要執行安裝之網路安裝點的完整路徑。包括 Location 屬性：</span><span class="sxs-lookup"><span data-stu-id="e91fa-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="e91fa-147">Location = "path"</span><span class="sxs-lookup"><span data-stu-id="e91fa-147">Location=”path”</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e91fa-148">下列範例顯示 Lync 2013 一般無訊息安裝的 Config.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="e91fa-148">The following example shows a Config.xml file for a typical silent installation of Lync 2013.</span></span>

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

<span data-ttu-id="e91fa-149">您可以在使用 Config.xml 檔案執行 Office 安裝及維護工作的詳細資訊 <https://go.microsoft.com/fwlink/p/?linkid=267514> 。</span><span class="sxs-lookup"><span data-stu-id="e91fa-149">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at <https://go.microsoft.com/fwlink/p/?linkid=267514>.</span></span>

<div>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="e91fa-150">自訂 Config.xml 檔案</span><span class="sxs-lookup"><span data-stu-id="e91fa-150">To customize the Config.xml file</span></span>

1.  <span data-ttu-id="e91fa-151">使用文字編輯器工具來開啟 Config.xml 檔案，例如 [記事本]。</span><span class="sxs-lookup"><span data-stu-id="e91fa-151">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2.  <span data-ttu-id="e91fa-152">找到包含您要變更之元素的那幾行。</span><span class="sxs-lookup"><span data-stu-id="e91fa-152">Locate the lines that contain the elements you want to change.</span></span>

3.  <span data-ttu-id="e91fa-153">以您要使用的無訊息選項來修改元素項目。</span><span class="sxs-lookup"><span data-stu-id="e91fa-153">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="e91fa-154">請務必移除批註定界符 " \<\!--" and "--\> "。</span><span class="sxs-lookup"><span data-stu-id="e91fa-154">Make sure that you remove the comment delimiters, "\<\!--" and "--\>".</span></span> <span data-ttu-id="e91fa-155">例如，使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="e91fa-155">For example, use the following syntax:</span></span>
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  <span data-ttu-id="e91fa-156">儲存 Config.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="e91fa-156">Save the Config.xml file.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

