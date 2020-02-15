---
title: Lync Server 2013： 登入和虛擬機器上使用 Lync 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e530f24150bac692717cefb2412712bf3bf8dd1c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a><span data-ttu-id="55a8e-102">登入和虛擬機器上使用 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="55a8e-102">Signing in and using Lync 2013 on the virtual machine</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55a8e-103">_**主題上次修改日期：** 2012年-10-03_</span><span class="sxs-lookup"><span data-stu-id="55a8e-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="55a8e-104">啟用 VDI 外掛程式後，當使用者登入 Lync 2013 時，也會進行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="55a8e-104">After the VDI plug-in is enabled, the following steps occur when the user signs in to Lync 2013.</span></span>

1.  <span data-ttu-id="55a8e-105">使用者輸入虛擬機器上執行 Lync 2013 用戶端中的他/她認證。</span><span class="sxs-lookup"><span data-stu-id="55a8e-105">The user types his or her credentials in to the Lync 2013 client running on the virtual machine.</span></span>

2.  <span data-ttu-id="55a8e-106">Lync 偵測到的可用性 VDI 外掛程式後，Lync 會提示使用者重新輸入他/她的認證。</span><span class="sxs-lookup"><span data-stu-id="55a8e-106">After Lync detects the availability of the VDI plug-in, Lync prompts the user to re-enter his or her credentials.</span></span> <span data-ttu-id="55a8e-107">建議使用者在此對話方塊中選取 **[儲存我的密碼]** 核取方塊，這樣在後續的登入中就不需要輸入認證。</span><span class="sxs-lookup"><span data-stu-id="55a8e-107">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>

3.  <span data-ttu-id="55a8e-108">Lync 開始與 VDI 外掛程式配對。</span><span class="sxs-lookup"><span data-stu-id="55a8e-108">Lync begins pairing with the VDI plug-in.</span></span> <span data-ttu-id="55a8e-109">配對完畢之前，用戶端會在 Lync 狀態列中顯示兩個圖示。</span><span class="sxs-lookup"><span data-stu-id="55a8e-109">Before pairing is complete, the client displays two icons in the Lync status bar.</span></span> <span data-ttu-id="55a8e-110">左下方的圖示表示沒有音訊裝置可用，右下方閃爍的圖示表示 VDI 配對在進行中，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="55a8e-110">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that the VDI pairing is in progress, as shown:</span></span>
    
    <span data-ttu-id="55a8e-111">![顯示成功配對的 Lync VDI 圖示](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "顯示成功配對的 Lync VDI 圖示")</span><span class="sxs-lookup"><span data-stu-id="55a8e-111">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>  

4.  <span data-ttu-id="55a8e-112">VDI 配對成功後，圖示會變更為表示音訊裝置將用於通話，以及 VDI 配對成功：</span><span class="sxs-lookup"><span data-stu-id="55a8e-112">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success:</span></span>
    
    <span data-ttu-id="55a8e-113">![Lync VDI 配對圖示顯示成功](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Lync VDI 配對圖示顯示成功")</span><span class="sxs-lookup"><span data-stu-id="55a8e-113">![Lync VDI pairing icon showing success](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Lync VDI pairing icon showing success")</span></span>  

5.  <span data-ttu-id="55a8e-114">Lync VDI 外掛程式配對之後，使用者可以在 Lync 相容的裝置連線至本機電腦上看到他/她的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="55a8e-114">After Lync pairs with the VDI plug-in, the user can see his or her presence on Lync compatible devices that are connected to the local computer.</span></span> <span data-ttu-id="55a8e-115">現在使用者就可以正常撥打及接聽通話。</span><span class="sxs-lookup"><span data-stu-id="55a8e-115">The user can now place and answer calls as usual.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

