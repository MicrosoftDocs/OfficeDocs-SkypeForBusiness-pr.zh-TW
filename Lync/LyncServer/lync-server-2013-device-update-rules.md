---
title: Lync Server 2013：裝置更新規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device Update rules
ms:assetid: a2f7e293-3342-4566-9605-410cb95f3b3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994062(v=OCS.15)
ms:contentKeyID: 51803973
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cce4b0be575665d23b2b09126905fc35791f61ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-rules-in-lync-server-2013"></a><span data-ttu-id="fccdc-102">Lync Server 2013 中的裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="fccdc-102">Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fccdc-103">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="fccdc-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="fccdc-104">Microsoft 會定期為 Lync Phone Edition 發行一組新的裝置固件更新。</span><span class="sxs-lookup"><span data-stu-id="fccdc-104">Periodically, Microsoft releases a new set of device firmware updates for Lync Phone Edition.</span></span> <span data-ttu-id="fccdc-105">*裝置更新規則*會將固件更新與硬體裝置（電話和其他執行 Lync Phone Edition 的裝置）進行關聯。</span><span class="sxs-lookup"><span data-stu-id="fccdc-105">*Device update rules* associate firmware updates with hardware devices—phones and other devices running Lync Phone Edition.</span></span>

<span data-ttu-id="fccdc-106">若要取得最新的裝置更新規則，請移至 Microsoft 網站上的 [說明及支援] 頁面，然後搜尋「手機版」。</span><span class="sxs-lookup"><span data-stu-id="fccdc-106">To get the latest set of device update rules, go to the Help and Support page on the Microsoft website, and search for "Phone Edition."</span></span> <span data-ttu-id="fccdc-107">下載更新套件，並將檔案解壓縮至電腦上要上傳更新的資料夾。</span><span class="sxs-lookup"><span data-stu-id="fccdc-107">Download the update package, and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="fccdc-108">解壓縮檔案之後，請匯入在解壓縮中找到的裝置更新規則。CAB 檔案（其名稱為 UCUpdates）。</span><span class="sxs-lookup"><span data-stu-id="fccdc-108">After the files have been extracted, import the device update rules found in the extracted .CAB file (which have the name UCUpdates.cab).</span></span> <span data-ttu-id="fccdc-109">接著，使用 Lync Server [控制台] 或 [Windows PowerShell Cmdlet] 來針對貴組織的裝置來查看及管理這些規則。</span><span class="sxs-lookup"><span data-stu-id="fccdc-109">Then, use the Lync Server Control Panel or Windows PowerShell cmdlets to view and manage these rules for your organization’s devices.</span></span>

<span data-ttu-id="fccdc-110">下列主題說明如何匯入、查看及管理裝置更新規則。</span><span class="sxs-lookup"><span data-stu-id="fccdc-110">The following topics tell you how to import, view, and manage device update rules.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fccdc-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="fccdc-111">In This Section</span></span>

  - [<span data-ttu-id="fccdc-112">在 Lync Server 2013 中查看裝置更新規則的相關資訊</span><span class="sxs-lookup"><span data-stu-id="fccdc-112">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)

  - [<span data-ttu-id="fccdc-113">在 Lync Server 2013 中匯入裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="fccdc-113">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)

  - [<span data-ttu-id="fccdc-114">在 Lync Server 2013 中核准裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="fccdc-114">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)

  - [<span data-ttu-id="fccdc-115">在 Lync Server 2013 中移除裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="fccdc-115">Remove a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-remove-a-device-update-rule.md)

  - [<span data-ttu-id="fccdc-116">在 Lync Server 2013 中重設裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="fccdc-116">Reset a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-reset-a-device-update-rule.md)

  - [<span data-ttu-id="fccdc-117">在 Lync Server 2013 中還原裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="fccdc-117">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

