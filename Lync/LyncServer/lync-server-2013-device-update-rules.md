---
title: Lync Server 2013： 裝置更新規則
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
ms.openlocfilehash: b52fa2f2aefae05f713972df5c3b15e6db7c0b57
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-rules-in-lync-server-2013"></a><span data-ttu-id="475d9-102">Lync Server 2013 中的裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="475d9-102">Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="475d9-103">_**上次修改主題：** 2013年-02-20 個_</span><span class="sxs-lookup"><span data-stu-id="475d9-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="475d9-104">定期，Microsoft Lync Phone Edition 的發行一組新的裝置韌體更新。</span><span class="sxs-lookup"><span data-stu-id="475d9-104">Periodically, Microsoft releases a new set of device firmware updates for Lync Phone Edition.</span></span> <span data-ttu-id="475d9-105">*裝置更新規則*將韌體更新關聯的硬體裝置 — 電話及其他執行 Lync Phone Edition 的裝置。</span><span class="sxs-lookup"><span data-stu-id="475d9-105">*Device update rules* associate firmware updates with hardware devices—phones and other devices running Lync Phone Edition.</span></span>

<span data-ttu-id="475d9-106">若要取得最新的裝置更新規則集，Microsoft 在網站上，移至 [說明及支援] 頁面上，並搜尋 「 Phone Edition 」。</span><span class="sxs-lookup"><span data-stu-id="475d9-106">To get the latest set of device update rules, go to the Help and Support page on the Microsoft website, and search for "Phone Edition."</span></span> <span data-ttu-id="475d9-107">下載更新套件，並將檔案解壓縮到資料夾之電腦上更新為可上傳。</span><span class="sxs-lookup"><span data-stu-id="475d9-107">Download the update package, and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="475d9-108">解壓縮檔案之後，匯入位於擷取裝置更新規則。CAB 檔案 （其中有名稱 UCUpdates.cab）。</span><span class="sxs-lookup"><span data-stu-id="475d9-108">After the files have been extracted, import the device update rules found in the extracted .CAB file (which have the name UCUpdates.cab).</span></span> <span data-ttu-id="475d9-109">然後，使用 Lync Server 控制台或 Windows PowerShell cmdlet 來檢視及管理貴組織的裝置的這些規則。</span><span class="sxs-lookup"><span data-stu-id="475d9-109">Then, use the Lync Server Control Panel or Windows PowerShell cmdlets to view and manage these rules for your organization’s devices.</span></span>

<span data-ttu-id="475d9-110">下列主題將告訴您如何匯入、 檢視及管理裝置更新規則。</span><span class="sxs-lookup"><span data-stu-id="475d9-110">The following topics tell you how to import, view, and manage device update rules.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="475d9-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="475d9-111">In This Section</span></span>

  - [<span data-ttu-id="475d9-112">檢視 Lync Server 2013 中的裝置更新規則的相關資訊</span><span class="sxs-lookup"><span data-stu-id="475d9-112">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)

  - [<span data-ttu-id="475d9-113">匯入 Lync Server 2013 中的裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="475d9-113">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)

  - [<span data-ttu-id="475d9-114">核准 Lync Server 2013 中的裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="475d9-114">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)

  - [<span data-ttu-id="475d9-115">移除 Lync Server 2013 中的裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="475d9-115">Remove a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-remove-a-device-update-rule.md)

  - [<span data-ttu-id="475d9-116">重設在 Lync Server 2013 中的裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="475d9-116">Reset a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-reset-a-device-update-rule.md)

  - [<span data-ttu-id="475d9-117">還原 Lync Server 2013 中的裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="475d9-117">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

