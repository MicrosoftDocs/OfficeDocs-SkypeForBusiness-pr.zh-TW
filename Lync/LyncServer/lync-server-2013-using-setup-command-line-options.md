---
title: Lync Server 2013：使用安裝程式命令列選項
description: Lync Server 2013：使用安裝程式命令列選項。
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
ms.openlocfilehash: 15c3490ead090766462ce83cb13ffe62355032cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580239"
---
# <a name="using-setup-command-line-options-in-lync-server-2013"></a><span data-ttu-id="9a992-103">在 Lync Server 2013 中使用安裝程式命令列選項</span><span class="sxs-lookup"><span data-stu-id="9a992-103">Using Setup command-line options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a992-104">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="9a992-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="9a992-105">Setup.exe 命令列將用於 Office 安裝中非常少的作業。</span><span class="sxs-lookup"><span data-stu-id="9a992-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="9a992-106">您通常會使用 Office 自訂工具和 Config.xml 檔案進行產品安裝和功能自訂，而不是使用安裝程式的命令列選項。</span><span class="sxs-lookup"><span data-stu-id="9a992-106">Instead of using the Setup command-line options, you’ll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>

<span data-ttu-id="9a992-107">Office Setup.exe 命令列會識別下表所述的命令列選項。</span><span class="sxs-lookup"><span data-stu-id="9a992-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>

### <a name="office-setup-command-line-options"></a><span data-ttu-id="9a992-108">Office 安裝程式 Command-Line 選項</span><span class="sxs-lookup"><span data-stu-id="9a992-108">Office Setup Command-Line Options</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a992-109">安裝 Command-Line 選項</span><span class="sxs-lookup"><span data-stu-id="9a992-109">Setup Command-Line Option</span></span></th>
<th><span data-ttu-id="9a992-110">描述</span><span class="sxs-lookup"><span data-stu-id="9a992-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a992-111">/admin</span><span class="sxs-lookup"><span data-stu-id="9a992-111">/admin</span></span></p></td>
<td><p><span data-ttu-id="9a992-112">執行 Office 自訂工具，以建立安裝程式自訂檔案 (.msp 檔案)。</span><span class="sxs-lookup"><span data-stu-id="9a992-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a992-113">/adminfile [path]</span><span class="sxs-lookup"><span data-stu-id="9a992-113">/adminfile [path]</span></span></p></td>
<td><p><span data-ttu-id="9a992-p102">將指定的安裝程式自訂檔案套用至安裝。您可以指定特定自訂檔案 (.msp 檔案) 的路徑，或是儲存自訂檔案的資料夾路徑。</span><span class="sxs-lookup"><span data-stu-id="9a992-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a992-116">/config [path]</span><span class="sxs-lookup"><span data-stu-id="9a992-116">/config [path]</span></span></p></td>
<td><p><span data-ttu-id="9a992-117">指定在安裝過程中，安裝程式所使用的 Config.xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="9a992-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="9a992-118">使用 [/config] 選項可指定您針對 Lync 2013 安裝所自訂的 Config.xml 檔案，例如： <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span><span class="sxs-lookup"><span data-stu-id="9a992-118">Use the /config option to specify the Config.xml file you customized for Lync 2013 installations, for example: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a992-119">/modify Lync</span><span class="sxs-lookup"><span data-stu-id="9a992-119">/modify Lync</span></span></p></td>
<td><p><span data-ttu-id="9a992-120">與修改的 Config.xml 檔案搭配使用，即可在維護模式中執行安裝程式，並對現有的 Office 安裝進行變更。</span><span class="sxs-lookup"><span data-stu-id="9a992-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="9a992-121">例如，您可以使用/modify 選項來新增或移除 Lync 功能。</span><span class="sxs-lookup"><span data-stu-id="9a992-121">For example, you can use the /modify option to add or remove Lync features.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a992-122">/repair Lync</span><span class="sxs-lookup"><span data-stu-id="9a992-122">/repair Lync</span></span></p></td>
<td><p><span data-ttu-id="9a992-123">從使用者的電腦執行安裝程式，以修復 Lync。</span><span class="sxs-lookup"><span data-stu-id="9a992-123">Runs Setup from the user’s computer to repair Lync.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a992-124">/uninstall Lync</span><span class="sxs-lookup"><span data-stu-id="9a992-124">/uninstall Lync</span></span></p></td>
<td><p><span data-ttu-id="9a992-125">執行安裝程式以從使用者的電腦中移除 Lync。</span><span class="sxs-lookup"><span data-stu-id="9a992-125">Runs Setup to remove Lync from the user’s computer.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9a992-126">如需使用安裝程式命令列選項的詳細資訊，請參閱 <https://go.microsoft.com/fwlink/p/?linkid=267515> 。</span><span class="sxs-lookup"><span data-stu-id="9a992-126">For details about using the setup command-line options, see <https://go.microsoft.com/fwlink/p/?linkid=267515>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

