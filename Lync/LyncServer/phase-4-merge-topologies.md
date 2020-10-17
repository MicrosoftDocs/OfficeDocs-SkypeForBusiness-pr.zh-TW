---
title: 階段4：合併拓撲
description: 階段4：合併拓撲。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: 'Phase 4: Merge topologies'
ms:assetid: 81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205044(v=OCS.15)
ms:contentKeyID: 48184668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 421cb83a57979ae677d4db76d2c8c3535f8e0dcb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571149"
---
# <a name="phase-4-merge-topologies"></a><span data-ttu-id="36298-103">階段4：合併拓撲</span><span class="sxs-lookup"><span data-stu-id="36298-103">Phase 4: Merge topologies</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36298-104">_**主題上次修改日期：** 2012-03-29_</span><span class="sxs-lookup"><span data-stu-id="36298-104">_**Topic Last Modified:** 2012-03-29_</span></span>

<span data-ttu-id="36298-105">下列主題概要說明將您的 Microsoft Office 通訊伺服器 2007 R2 集區合併至 Microsoft Lync Server 2013 集區所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="36298-105">The following topics outline the steps needed to merge your Microsoft Office Communications Server 2007 R2 pools to Microsoft Lync Server 2013 pools.</span></span> <span data-ttu-id="36298-106">首先，您要使用「[拓撲產生器合併精靈」來合併拓撲資訊。</span><span class="sxs-lookup"><span data-stu-id="36298-106">First, you use the Topology Builder Merge wizard to merge topology information.</span></span> <span data-ttu-id="36298-107">這個工具會收集有關您的 Office 通訊伺服器 2007 R2 環境的資訊，包括 Edge Server 資訊，並將該資訊發佈至與 Lync Server 2013 共用的資料庫。</span><span class="sxs-lookup"><span data-stu-id="36298-107">This tool collects information about your Office Communications Server 2007 R2 environment, including Edge Server information, and publishes that information to a database shared with Lync Server 2013.</span></span> <span data-ttu-id="36298-108">在您發佈合併後的拓撲之後，拓撲產生器是用來查看 Office 通訊伺服器 2007 R2 拓撲資訊，以及有關新近部署的 Lync Server 2013 拓撲的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="36298-108">After you publish the merged topology, Topology Builder is used to view the Office Communications Server 2007 R2 topology information and information about the newly deployed Lync Server 2013 topology.</span></span> <span data-ttu-id="36298-109">最後，您可使用 Lync Server 管理命令介面 Cmdlet，匯入原則與組態設定。</span><span class="sxs-lookup"><span data-stu-id="36298-109">Finally, you use Lync Server Management Shell cmdlets to import policies and configuration settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="36298-110">本節內容</span><span class="sxs-lookup"><span data-stu-id="36298-110">In This Section</span></span>

  - [<span data-ttu-id="36298-111">安裝 WMI 回溯相容性套件</span><span class="sxs-lookup"><span data-stu-id="36298-111">Install WMI Backward Compatibility package</span></span>](install-wmi-backward-compatibility-package.md)

  - [<span data-ttu-id="36298-112">使用拓撲產生器合併嚮導進行合併</span><span class="sxs-lookup"><span data-stu-id="36298-112">Merge using Topology Builder Merge wizard</span></span>](merge-using-topology-builder-merge-wizard.md)

  - [<span data-ttu-id="36298-113">匯入原則及設定</span><span class="sxs-lookup"><span data-stu-id="36298-113">Import policies and settings</span></span>](import-policies-and-settings.md)

  - [<span data-ttu-id="36298-114">確認拓撲資訊</span><span class="sxs-lookup"><span data-stu-id="36298-114">Verify topology information</span></span>](verify-topology-information.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

