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
ms.openlocfilehash: 0643c0d7da4dbed734bfd098cc2a585e018bf0cd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532940"
---
# <a name="test-voice-routing-in-lync-server-2013"></a><span data-ttu-id="6fd95-102">在 Lync Server 2013 中測試語音路由</span><span class="sxs-lookup"><span data-stu-id="6fd95-102">Test voice routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fd95-103">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="6fd95-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="6fd95-104">您可以使用 Lync Server 控制台的 [ **測試語音路由** ] 索引標籤來設定測試案例案例。</span><span class="sxs-lookup"><span data-stu-id="6fd95-104">You can use the Lync Server Control Panel **Test Voice Routing** tab to configure test case scenarios.</span></span> <span data-ttu-id="6fd95-105">若要定義測試案例，您可以指定要測試指定電話號碼的撥號對應表、語音原則、PSTN 使用方式及語音路由。</span><span class="sxs-lookup"><span data-stu-id="6fd95-105">To define a test case, you specify the dial plan, voice policy, PSTN usage, and voice route against which to test a specified phone number.</span></span>

<span data-ttu-id="6fd95-106">在您實際部署語音路由設定之前，我們建議您在不同的電話號碼上進行測試，以確定結果是您預期的結果。</span><span class="sxs-lookup"><span data-stu-id="6fd95-106">Before you actually deploy your voice routing configuration, we recommend that you test it on various phone numbers to make sure that the results are what you're expecting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="6fd95-107">您可以使用 [ <STRONG>匯出測試案例</STRONG> ] 和 [匯 <STRONG>入測試案例</STRONG> ] 命令儲存語音路由測試案例，並將其匯入供其他電腦使用。</span><span class="sxs-lookup"><span data-stu-id="6fd95-107">You can use the <STRONG>Export test cases</STRONG> and <STRONG>Import test cases</STRONG> commands to save voice routing test cases and import them for use on another computer.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="6fd95-108">如果您刪除任何部分的語音路由設定，例如撥號對應表、語音原則、語音路由或電話使用狀況，您應該檢查並更新您的語音路由測試案例。</span><span class="sxs-lookup"><span data-stu-id="6fd95-108">If you delete any part of your voice routing configuration, such as a dial plan, voice policy, voice route, or phone usage, you should review and update your voice routing test cases.</span></span> <span data-ttu-id="6fd95-109">Lync Server 控制台不會提醒您由於設定變更而不再有效的測試案例。</span><span class="sxs-lookup"><span data-stu-id="6fd95-109">The Lync Server Control Panel will not alert you to test cases that are no longer valid due to changed configurations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6fd95-110">本章節內容</span><span class="sxs-lookup"><span data-stu-id="6fd95-110">In This Section</span></span>

  - [<span data-ttu-id="6fd95-111">在 Lync Server 2013 中建立語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="6fd95-111">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)

  - [<span data-ttu-id="6fd95-112">在 Lync Server 2013 中匯出語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="6fd95-112">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)

  - [<span data-ttu-id="6fd95-113">在 Lync Server 2013 中匯入語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="6fd95-113">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)

  - [<span data-ttu-id="6fd95-114">在 Lync Server 2013 中執行語音路由測試</span><span class="sxs-lookup"><span data-stu-id="6fd95-114">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

