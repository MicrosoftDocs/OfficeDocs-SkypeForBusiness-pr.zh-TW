---
title: 匯入原則及設定
description: 匯入原則與設定。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e014b7e8f0498742104118eec9eb313394ae6a94
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569029"
---
# <a name="import-policies-and-settings"></a><span data-ttu-id="3b53b-103">匯入原則及設定</span><span class="sxs-lookup"><span data-stu-id="3b53b-103">Import policies and settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b53b-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3b53b-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3b53b-105">在您將 Office 通訊伺服器 2007 R2 拓撲資訊與您的 Lync Server 2013 試驗集區合併之後，您必須執行 Lync Server 2013 管理命令介面 Cmdlet，將您的 Office 通訊伺服器 2007 R2 原則和設定值遷移至 Lync Server 2013 試驗集區。</span><span class="sxs-lookup"><span data-stu-id="3b53b-105">After you merge your Office Communications Server 2007 R2 topology information with your Lync Server 2013 pilot pool, you need to run a Lync Server 2013 Management Shell cmdlet to migrate your Office Communications Server 2007 R2 policies and configuration settings to your Lync Server 2013 pilot pool.</span></span>

<span data-ttu-id="3b53b-106">**Import-CsLegacyConfiguration** Cmdlet 會將原則、語音路由、撥號對應表、Communicator Web Access URLs 和撥入存取號碼匯入 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="3b53b-106">The **Import-CsLegacyConfiguration** cmdlet imports policies, voice routes, dial plans, Communicator Web Access URLs, and dial-in access numbers to Lync Server 2013.</span></span>

<div>

## <a name="to-migrate-policies-and-settings"></a><span data-ttu-id="3b53b-107">移轉原則與設定</span><span class="sxs-lookup"><span data-stu-id="3b53b-107">To migrate policies and settings</span></span>

1.  <span data-ttu-id="3b53b-108">在 Lync Server 2013 前端伺服器上，啟動 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="3b53b-108">On the Lync Server 2013 Front End server, start the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="3b53b-109">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="3b53b-109">At the command line, type the following:</span></span>
    
        Import-CsLegacyConfiguration
    
    <span data-ttu-id="3b53b-110">在匯入原則之後，請使用下列程式，在 Lync Server [控制台] 中查看匯入的原則。</span><span class="sxs-lookup"><span data-stu-id="3b53b-110">After the policies are imported, use the procedure that follows to see the imported policies in the Lync Server Control Panel .</span></span>

</div>

<div>

## <a name="to-view-imported-policies"></a><span data-ttu-id="3b53b-111">檢視匯入的原則</span><span class="sxs-lookup"><span data-stu-id="3b53b-111">To view imported policies</span></span>

1.  <span data-ttu-id="3b53b-112">開啟 [Lync Server 2013 控制台]。</span><span class="sxs-lookup"><span data-stu-id="3b53b-112">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="3b53b-113">按一下 [語音路由]\*\*\*\*，然後檢視匯入的原則。</span><span class="sxs-lookup"><span data-stu-id="3b53b-113">Click **Voice Routing** and view the imported policies.</span></span>

3.  <span data-ttu-id="3b53b-114">按一下 [會議]\*\*\*\*，然後檢視匯入的原則。</span><span class="sxs-lookup"><span data-stu-id="3b53b-114">Click **Conferencing** and view the imported policies.</span></span>

4.  <span data-ttu-id="3b53b-115">按一下 [ **同盟和外部存取** ]，然後查看已匯入的原則。</span><span class="sxs-lookup"><span data-stu-id="3b53b-115">Click **Federation and External Access** and view the imported policies.</span></span>

5.  <span data-ttu-id="3b53b-116">按一下 [監控和封存]\*\*\*\*，然後檢視匯入的原則。</span><span class="sxs-lookup"><span data-stu-id="3b53b-116">Click **Monitoring and Archiving** and view the imported policies.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

