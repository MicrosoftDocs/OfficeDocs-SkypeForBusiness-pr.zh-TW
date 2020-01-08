---
title: Lync Server 2013：在虛擬機器上登入和使用 Lync 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3b890f008b30ecf008bd2e6f03803fbfe6c1674
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975877"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a><span data-ttu-id="4c029-102">在虛擬機器上登入和使用 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="4c029-102">Signing in and using Lync 2013 on the virtual machine</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c029-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="4c029-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="4c029-104">啟用 VDI 外掛程式之後，當使用者登入 Lync 2013 時，會發生下列步驟。</span><span class="sxs-lookup"><span data-stu-id="4c029-104">After the VDI plug-in is enabled, the following steps occur when the user signs in to Lync 2013.</span></span>

1.  <span data-ttu-id="4c029-105">使用者在虛擬機器上執行的 Lync 2013 用戶端輸入其認證。</span><span class="sxs-lookup"><span data-stu-id="4c029-105">The user types his or her credentials in to the Lync 2013 client running on the virtual machine.</span></span>

2.  <span data-ttu-id="4c029-106">Lync 偵測到 VDI 外掛程式的可用性之後，Lync 會提示使用者重新輸入其認證。</span><span class="sxs-lookup"><span data-stu-id="4c029-106">After Lync detects the availability of the VDI plug-in, Lync prompts the user to re-enter his or her credentials.</span></span> <span data-ttu-id="4c029-107">在這個對話方塊中，我們建議使用者選取 [**儲存我的密碼**] 核取方塊，以便在進行後續登入時，系統不會要求您輸入認證。</span><span class="sxs-lookup"><span data-stu-id="4c029-107">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>

3.  <span data-ttu-id="4c029-108">Lync 會從 VDI 外掛程式開始配對。</span><span class="sxs-lookup"><span data-stu-id="4c029-108">Lync begins pairing with the VDI plug-in.</span></span> <span data-ttu-id="4c029-109">配對完成之前，用戶端會在 Lync 狀態列中顯示兩個圖示。</span><span class="sxs-lookup"><span data-stu-id="4c029-109">Before pairing is complete, the client displays two icons in the Lync status bar.</span></span> <span data-ttu-id="4c029-110">左下角的圖示表示沒有可用的音訊裝置，右下方的閃爍圖示則表示正在進行 VDI 配對，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4c029-110">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that the VDI pairing is in progress, as shown:</span></span>
    
    <span data-ttu-id="4c029-111">![LYNC vdi 圖示，顯示成功]配對的(images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "lync vdi 圖示顯示成功配對")</span><span class="sxs-lookup"><span data-stu-id="4c029-111">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>  

4.  <span data-ttu-id="4c029-112">在已成功進行 VDI 配對之後，圖示會變更，以指出將用於通話的音訊裝置和 VDI 配對成功：</span><span class="sxs-lookup"><span data-stu-id="4c029-112">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success:</span></span>
    
    <span data-ttu-id="4c029-113">![LYNC vdi 配對圖示，顯示成功]的(images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "lync vdi 配對圖示（顯示成功")）</span><span class="sxs-lookup"><span data-stu-id="4c029-113">![Lync VDI pairing icon showing success](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Lync VDI pairing icon showing success")</span></span>  

5.  <span data-ttu-id="4c029-114">在 Lync 對使用 VDI 外掛程式之後，使用者可以在連線至本機電腦的 Lync 相容裝置上看到他或她的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="4c029-114">After Lync pairs with the VDI plug-in, the user can see his or her presence on Lync compatible devices that are connected to the local computer.</span></span> <span data-ttu-id="4c029-115">使用者現在可以照常進行呼叫並接聽通話。</span><span class="sxs-lookup"><span data-stu-id="4c029-115">The user can now place and answer calls as usual.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

