---
title: Lync Server 2013： 測試語音路由
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
ms.openlocfilehash: 5b45f52a07713973d8f642389513d0e34b5236de
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-routing-in-lync-server-2013"></a><span data-ttu-id="f9e84-102">測試 Lync Server 2013 中的語音路由</span><span class="sxs-lookup"><span data-stu-id="f9e84-102">Test voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9e84-103">_**上次修改主題：** 2013年-02-24_</span><span class="sxs-lookup"><span data-stu-id="f9e84-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="f9e84-104">您可以使用 [Lync Server Control Panel**測試語音路由**] 索引標籤來設定測試案例的案例。</span><span class="sxs-lookup"><span data-stu-id="f9e84-104">You can use the Lync Server Control Panel **Test Voice Routing** tab to configure test case scenarios.</span></span> <span data-ttu-id="f9e84-105">若要定義測試案例，您可以指定撥號對應表、 語音原則、 PSTN 使用方式，並針對其測試指定的電話號碼的語音路由。</span><span class="sxs-lookup"><span data-stu-id="f9e84-105">To define a test case, you specify the dial plan, voice policy, PSTN usage, and voice route against which to test a specified phone number.</span></span>

<span data-ttu-id="f9e84-106">在實際部署語音路由設定之前，建議您先在不同的電話號碼，以確定是您所預期的結果進行測試。</span><span class="sxs-lookup"><span data-stu-id="f9e84-106">Before you actually deploy your voice routing configuration, we recommend that you test it on various phone numbers to make sure that the results are what you're expecting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="f9e84-107">您可以使用 [<STRONG>匯出測試案例</STRONG>，並<STRONG>匯入測試案例</STRONG>命令，以儲存語音路由測試案例，並匯入的使用在另一部電腦上。</span><span class="sxs-lookup"><span data-stu-id="f9e84-107">You can use the <STRONG>Export test cases</STRONG> and <STRONG>Import test cases</STRONG> commands to save voice routing test cases and import them for use on another computer.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="f9e84-108">如果您刪除任何一部分語音路由設定，例如撥號對應表、 語音原則、 語音路由] 或電話使用方式，您應該檢閱並更新您的語音路由測試案例。</span><span class="sxs-lookup"><span data-stu-id="f9e84-108">If you delete any part of your voice routing configuration, such as a dial plan, voice policy, voice route, or phone usage, you should review and update your voice routing test cases.</span></span> <span data-ttu-id="f9e84-109">Lync Server 控制台不會警示您測試已不再有效，因為變更組態的情況。</span><span class="sxs-lookup"><span data-stu-id="f9e84-109">The Lync Server Control Panel will not alert you to test cases that are no longer valid due to changed configurations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f9e84-110">本章節內容</span><span class="sxs-lookup"><span data-stu-id="f9e84-110">In This Section</span></span>

  - [<span data-ttu-id="f9e84-111">在 Lync Server 2013 中建立語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="f9e84-111">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)

  - [<span data-ttu-id="f9e84-112">匯出語音路由測試案例在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9e84-112">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)

  - [<span data-ttu-id="f9e84-113">匯入 Lync Server 2013 中的語音路由測試案例</span><span class="sxs-lookup"><span data-stu-id="f9e84-113">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)

  - [<span data-ttu-id="f9e84-114">在 Lync Server 2013 中執行語音路由測試</span><span class="sxs-lookup"><span data-stu-id="f9e84-114">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

