---
title: 匯入原則和設定
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f4a4d86d687236934c319e3fb7bd5e6c8027a73
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-policies-and-settings"></a><span data-ttu-id="572ae-102">匯入原則和設定</span><span class="sxs-lookup"><span data-stu-id="572ae-102">Import policies and settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="572ae-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="572ae-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="572ae-104">在您將 Office 通訊伺服器 2007 R2 拓撲資訊與 Lync Server 2013 試驗池合併之後，您必須執行 Lync Server 2013 管理命令介面 Cmdlet，以遷移您的 Office 通訊伺服器 2007 R2 原則和設定設定移至您的 Lync Server 2013 試生產池。</span><span class="sxs-lookup"><span data-stu-id="572ae-104">After you merge your Office Communications Server 2007 R2 topology information with your Lync Server 2013 pilot pool, you need to run a Lync Server 2013 Management Shell cmdlet to migrate your Office Communications Server 2007 R2 policies and configuration settings to your Lync Server 2013 pilot pool.</span></span>

<span data-ttu-id="572ae-105">匯**入-CsLegacyConfiguration** Cmdlet 會將原則、語音路由、撥號方案、Communicator Web Access url，以及撥入存取號碼匯入 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="572ae-105">The **Import-CsLegacyConfiguration** cmdlet imports policies, voice routes, dial plans, Communicator Web Access URLs, and dial-in access numbers to Lync Server 2013.</span></span>

<div>

## <a name="to-migrate-policies-and-settings"></a><span data-ttu-id="572ae-106">遷移原則和設定</span><span class="sxs-lookup"><span data-stu-id="572ae-106">To migrate policies and settings</span></span>

1.  <span data-ttu-id="572ae-107">在 Lync Server 2013 前端伺服器上，啟動 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="572ae-107">On the Lync Server 2013 Front End server, start the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="572ae-108">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="572ae-108">At the command line, type the following:</span></span>
    
        Import-CsLegacyConfiguration
    
    <span data-ttu-id="572ae-109">匯入原則之後，請使用下列程式，查看 Lync Server 控制台中的匯入原則。</span><span class="sxs-lookup"><span data-stu-id="572ae-109">After the policies are imported, use the procedure that follows to see the imported policies in the Lync Server Control Panel .</span></span>

</div>

<div>

## <a name="to-view-imported-policies"></a><span data-ttu-id="572ae-110">若要查看匯入的原則</span><span class="sxs-lookup"><span data-stu-id="572ae-110">To view imported policies</span></span>

1.  <span data-ttu-id="572ae-111">開啟 Lync Server 2013 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="572ae-111">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="572ae-112">按一下 [**語音路由**] 並查看已匯入的原則。</span><span class="sxs-lookup"><span data-stu-id="572ae-112">Click **Voice Routing** and view the imported policies.</span></span>

3.  <span data-ttu-id="572ae-113">按一下 [**會議**] 並查看已匯入的原則。</span><span class="sxs-lookup"><span data-stu-id="572ae-113">Click **Conferencing** and view the imported policies.</span></span>

4.  <span data-ttu-id="572ae-114">按一下 [**同盟與外部存取**] 並查看匯入的原則。</span><span class="sxs-lookup"><span data-stu-id="572ae-114">Click **Federation and External Access** and view the imported policies.</span></span>

5.  <span data-ttu-id="572ae-115">按一下 [**監視及**封存]，然後查看匯入的原則。</span><span class="sxs-lookup"><span data-stu-id="572ae-115">Click **Monitoring and Archiving** and view the imported policies.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

