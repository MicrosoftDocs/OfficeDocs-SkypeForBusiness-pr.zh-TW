---
title: Lync Server 2013：裝置更新規則
description: Lync Server 2013：裝置更新規則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update rules
ms:assetid: a2f7e293-3342-4566-9605-410cb95f3b3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994062(v=OCS.15)
ms:contentKeyID: 51803973
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd6d34c290f4a08f67143294fcc5dd18e1acf9d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565959"
---
# <a name="device-update-rules-in-lync-server-2013"></a><span data-ttu-id="5b939-103">Lync Server 2013 中的裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="5b939-103">Device Update rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b939-104">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="5b939-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="5b939-105">Microsoft 會定期為 Lync Phone Edition 發行一組新的裝置固件更新。</span><span class="sxs-lookup"><span data-stu-id="5b939-105">Periodically, Microsoft releases a new set of device firmware updates for Lync Phone Edition.</span></span> <span data-ttu-id="5b939-106">*裝置更新規則* 會將固件更新與硬體裝置（電話及其他執行 Lync Phone Edition 的裝置）產生關聯。</span><span class="sxs-lookup"><span data-stu-id="5b939-106">*Device update rules* associate firmware updates with hardware devices—phones and other devices running Lync Phone Edition.</span></span>

<span data-ttu-id="5b939-107">若要取得最新的裝置更新規則集，請移至 Microsoft 網站上的 [說明與支援] 頁面，然後搜尋「Phone Edition」。</span><span class="sxs-lookup"><span data-stu-id="5b939-107">To get the latest set of device update rules, go to the Help and Support page on the Microsoft website, and search for "Phone Edition."</span></span> <span data-ttu-id="5b939-108">下載更新套件，並將檔案解壓縮至要上傳更新之電腦上的資料夾。</span><span class="sxs-lookup"><span data-stu-id="5b939-108">Download the update package, and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="5b939-109">解壓縮檔案之後，請匯入解壓縮中所找到的裝置更新規則。UCUpdates.cab) 名稱的 CAB 檔 (。</span><span class="sxs-lookup"><span data-stu-id="5b939-109">After the files have been extracted, import the device update rules found in the extracted .CAB file (which have the name UCUpdates.cab).</span></span> <span data-ttu-id="5b939-110">然後，使用 Lync Server 控制台或 Windows PowerShell Cmdlet，以查看及管理組織裝置的這些規則。</span><span class="sxs-lookup"><span data-stu-id="5b939-110">Then, use the Lync Server Control Panel or Windows PowerShell cmdlets to view and manage these rules for your organization’s devices.</span></span>

<span data-ttu-id="5b939-111">下列主題告訴您如何匯入、查看及管理裝置更新規則。</span><span class="sxs-lookup"><span data-stu-id="5b939-111">The following topics tell you how to import, view, and manage device update rules.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5b939-112">本章節內容</span><span class="sxs-lookup"><span data-stu-id="5b939-112">In This Section</span></span>

  - [<span data-ttu-id="5b939-113">在 Lync Server 2013 中查看裝置更新規則的相關資訊</span><span class="sxs-lookup"><span data-stu-id="5b939-113">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)

  - [<span data-ttu-id="5b939-114">在 Lync Server 2013 中匯入裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="5b939-114">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)

  - [<span data-ttu-id="5b939-115">核准 Lync Server 2013 中的裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="5b939-115">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)

  - [<span data-ttu-id="5b939-116">在 Lync Server 2013 中移除裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="5b939-116">Remove a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-remove-a-device-update-rule.md)

  - [<span data-ttu-id="5b939-117">在 Lync Server 2013 中重設裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="5b939-117">Reset a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-reset-a-device-update-rule.md)

  - [<span data-ttu-id="5b939-118">在 Lync Server 2013 中還原裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="5b939-118">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

