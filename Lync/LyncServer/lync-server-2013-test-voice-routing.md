---
title: Lync Server 2013：測試語音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice routing
ms:assetid: d3aae909-fef6-440f-b144-0b62dc82bf5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398915(v=OCS.15)
ms:contentKeyID: 48185444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b27fc4f3dfc42e9187ea0aee801b3c2115d83ff0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-routing-in-lync-server-2013"></a><span data-ttu-id="2c063-102">在 Lync Server 2013 中測試語音路由</span><span class="sxs-lookup"><span data-stu-id="2c063-102">Test voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c063-103">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="2c063-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="2c063-104">您可以使用 Lync Server 的 [控制台]**測試 [語音路由**] 索引標籤來設定測試案例案例。</span><span class="sxs-lookup"><span data-stu-id="2c063-104">You can use the Lync Server Control Panel **Test Voice Routing** tab to configure test case scenarios.</span></span> <span data-ttu-id="2c063-105">若要定義測試案例，您可以指定撥號計畫、語音原則、PSTN 使用及語音路由，以測試指定的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="2c063-105">To define a test case, you specify the dial plan, voice policy, PSTN usage, and voice route against which to test a specified phone number.</span></span>

<span data-ttu-id="2c063-106">在您實際部署您的語音路由設定之前，建議您在各種電話號碼上測試，以確保結果符合您的預期。</span><span class="sxs-lookup"><span data-stu-id="2c063-106">Before you actually deploy your voice routing configuration, we recommend that you test it on various phone numbers to make sure that the results are what you're expecting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="2c063-107">您可以使用 [<STRONG>匯出測試案例</STRONG>] 和 [匯<STRONG>入測試案例</STRONG>] 命令來儲存語音路由測試案例，並將它們匯入以供在其他電腦上使用。</span><span class="sxs-lookup"><span data-stu-id="2c063-107">You can use the <STRONG>Export test cases</STRONG> and <STRONG>Import test cases</STRONG> commands to save voice routing test cases and import them for use on another computer.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="2c063-108">如果您刪除任何部分的語音路由設定，例如撥號方案、語音原則、語音路線或電話使用方式，您應該查看並更新您的語音路由測試案例。</span><span class="sxs-lookup"><span data-stu-id="2c063-108">If you delete any part of your voice routing configuration, such as a dial plan, voice policy, voice route, or phone usage, you should review and update your voice routing test cases.</span></span> <span data-ttu-id="2c063-109">Lync Server [控制台] 不會提醒您由於配置已變更而不再有效的測試案例。</span><span class="sxs-lookup"><span data-stu-id="2c063-109">The Lync Server Control Panel will not alert you to test cases that are no longer valid due to changed configurations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2c063-110">本節內容</span><span class="sxs-lookup"><span data-stu-id="2c063-110">In This Section</span></span>

  - [<span data-ttu-id="2c063-111">在 Lync Server 2013 中建立語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="2c063-111">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)

  - [<span data-ttu-id="2c063-112">在 Lync Server 2013 中匯出語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="2c063-112">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)

  - [<span data-ttu-id="2c063-113">在 Lync Server 2013 中改善語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="2c063-113">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)

  - [<span data-ttu-id="2c063-114">在 Lync Server 2013 中執行語音路由測試</span><span class="sxs-lookup"><span data-stu-id="2c063-114">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

