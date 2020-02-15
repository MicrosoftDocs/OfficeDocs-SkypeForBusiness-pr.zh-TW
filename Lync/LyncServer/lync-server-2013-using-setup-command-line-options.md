---
title: Lync Server 2013： 使用安裝程式命令列選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aacaa402b325fbefe13d70dea4f3e74af1d896cb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-setup-command-line-options-in-lync-server-2013"></a><span data-ttu-id="d4a2c-102">在 Lync Server 2013 中使用 Setup 命令列選項</span><span class="sxs-lookup"><span data-stu-id="d4a2c-102">Using Setup command-line options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4a2c-103">_**主題上次修改日期：** 2012年-10-03_</span><span class="sxs-lookup"><span data-stu-id="d4a2c-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="d4a2c-104">在 Office 安裝程式操作很少使用 Setup.exe 命令列。</span><span class="sxs-lookup"><span data-stu-id="d4a2c-104">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="d4a2c-105">而不是使用安裝程式命令列選項，您通常會針對產品安裝程式和功能自訂使用 Office 自訂工具和 Config.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="d4a2c-105">Instead of using the Setup command-line options, you’ll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>

<span data-ttu-id="d4a2c-106">Office Setup.exe 命令列可辨識下表所述的命令列選項。</span><span class="sxs-lookup"><span data-stu-id="d4a2c-106">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>

### <a name="office-setup-command-line-options"></a><span data-ttu-id="d4a2c-107">Office 安裝程式命令列選項</span><span class="sxs-lookup"><span data-stu-id="d4a2c-107">Office Setup Command-Line Options</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4a2c-108">安裝程式命令列選項</span><span class="sxs-lookup"><span data-stu-id="d4a2c-108">Setup Command-Line Option</span></span></th>
<th><span data-ttu-id="d4a2c-109">描述</span><span class="sxs-lookup"><span data-stu-id="d4a2c-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4a2c-110">/admin</span><span class="sxs-lookup"><span data-stu-id="d4a2c-110">/admin</span></span></p></td>
<td><p><span data-ttu-id="d4a2c-111">執行 Office 自訂工具，以建立安裝程式自訂檔案 (.msp 檔案)。</span><span class="sxs-lookup"><span data-stu-id="d4a2c-111">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4a2c-112">/adminfile [path]</span><span class="sxs-lookup"><span data-stu-id="d4a2c-112">/adminfile [path]</span></span></p></td>
<td><p><span data-ttu-id="d4a2c-p102">將指定的安裝程式自訂檔案套用至安裝。您可以指定特定自訂檔案 (.msp 檔案) 的路徑，或是儲存自訂檔案的資料夾路徑。</span><span class="sxs-lookup"><span data-stu-id="d4a2c-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4a2c-115">/config [path]</span><span class="sxs-lookup"><span data-stu-id="d4a2c-115">/config [path]</span></span></p></td>
<td><p><span data-ttu-id="d4a2c-116">指定在安裝過程中，安裝程式所使用的 Config.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="d4a2c-116">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="d4a2c-117">/Config 選項可用於指定例如 Lync 2013 的安裝中，為自訂的 Config.xml 檔案：<code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span><span class="sxs-lookup"><span data-stu-id="d4a2c-117">Use the /config option to specify the Config.xml file you customized for Lync 2013 installations, for example: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4a2c-118">/ 修改 Lync</span><span class="sxs-lookup"><span data-stu-id="d4a2c-118">/modify Lync</span></span></p></td>
<td><p><span data-ttu-id="d4a2c-119">與修改的 Config.xml 檔案搭配使用，即可在維護模式中執行安裝程式，並對現有的 Office 安裝進行變更。</span><span class="sxs-lookup"><span data-stu-id="d4a2c-119">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="d4a2c-120">例如，您可以使用 / 修改選項來新增或移除 Lync 功能。</span><span class="sxs-lookup"><span data-stu-id="d4a2c-120">For example, you can use the /modify option to add or remove Lync features.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4a2c-121">/ 修復 Lync</span><span class="sxs-lookup"><span data-stu-id="d4a2c-121">/repair Lync</span></span></p></td>
<td><p><span data-ttu-id="d4a2c-122">會從以修復 Lync 使用者的電腦執行安裝程式。</span><span class="sxs-lookup"><span data-stu-id="d4a2c-122">Runs Setup from the user’s computer to repair Lync.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4a2c-123">解除安裝 Lync /</span><span class="sxs-lookup"><span data-stu-id="d4a2c-123">/uninstall Lync</span></span></p></td>
<td><p><span data-ttu-id="d4a2c-124">執行安裝程式，從使用者電腦移除 Lync。</span><span class="sxs-lookup"><span data-stu-id="d4a2c-124">Runs Setup to remove Lync from the user’s computer.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d4a2c-125">如需使用安裝程式命令列選項的詳細資訊，請參閱<http://go.microsoft.com/fwlink/p/?linkid=267515>。</span><span class="sxs-lookup"><span data-stu-id="d4a2c-125">For details about using the setup command-line options, see <http://go.microsoft.com/fwlink/p/?linkid=267515>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

