---
title: 移除授權主項目目
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove an authorized host entry
ms:assetid: 56a04140-347e-4eef-bede-0e858534f71e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204902(v=OCS.15)
ms:contentKeyID: 48184177
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd64239460d76d63b28bb3a3abeb8c5cc8bb97d9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-an-authorized-host-entry"></a><span data-ttu-id="0f3dc-102">移除授權主項目目</span><span class="sxs-lookup"><span data-stu-id="0f3dc-102">Remove an authorized host entry</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f3dc-103">_**主題上次修改日期：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="0f3dc-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="0f3dc-104">本主題說明如何移除舊版授權主項目目（稱為 Lync Server 2013 中的*信任應用程式專案*）。</span><span class="sxs-lookup"><span data-stu-id="0f3dc-104">This topic describes how to remove a legacy authorized host entry (known as a *trusted application entry* in Lync Server 2013).</span></span> <span data-ttu-id="0f3dc-105">當您將遠端呼叫控制遷移至 Lync Server 2013 部署時，您必須移除 Office 通訊伺服器 2007 R2 部署中任何 SIP/CSTA 閘道的現有授權主項目目。</span><span class="sxs-lookup"><span data-stu-id="0f3dc-105">You must remove existing authorized host entries for any SIP/CSTA gateways in your Office Communications Server 2007 R2 deployment when you migrate remote call control to a Lync Server 2013 deployment.</span></span> <span data-ttu-id="0f3dc-106">您必須使用 Office 通訊伺服器 2007 R2 隨附的系統管理工具，才能移除現有的授權主項目目。</span><span class="sxs-lookup"><span data-stu-id="0f3dc-106">You must use the administrative tools included with Office Communications Server 2007 R2 to remove the existing authorized host entries.</span></span>

<div>

## <a name="to-remove-an-authorized-host-entry-in-an-office-communications-server-2007-r2-deployment"></a><span data-ttu-id="0f3dc-107">若要移除 Office Communications Server 2007 R2 部署中的授權主機項目</span><span class="sxs-lookup"><span data-stu-id="0f3dc-107">To remove an authorized host entry in an Office Communications Server 2007 R2 deployment</span></span>

1.  <span data-ttu-id="0f3dc-108">開啟 Office 通訊伺服器 2007 R2 管理主控台。</span><span class="sxs-lookup"><span data-stu-id="0f3dc-108">Open the Office Communications Server 2007 R2 administrative console.</span></span>

2.  <span data-ttu-id="0f3dc-109">展開樹狀結構，並且以滑鼠右鍵按一下授權主機建立所在的集區。</span><span class="sxs-lookup"><span data-stu-id="0f3dc-109">Expand the tree and right-click the pool where the authorized host was created.</span></span>

3.  <span data-ttu-id="0f3dc-110">按一下 **[屬性]**，再按一下 [前端屬性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f3dc-110">Click **Properties**, and then click **Front End Properties**.</span></span>

4.  <span data-ttu-id="0f3dc-111">按一下 **[主機授權]** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="0f3dc-111">Click the **Host Authorization** tab.</span></span>

5.  <span data-ttu-id="0f3dc-112">選取伺服器，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="0f3dc-112">Select a server, and then click **Remove**.</span></span>

6.  <span data-ttu-id="0f3dc-113">在 **[屬性]** 中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="0f3dc-113">In **Properties**, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

