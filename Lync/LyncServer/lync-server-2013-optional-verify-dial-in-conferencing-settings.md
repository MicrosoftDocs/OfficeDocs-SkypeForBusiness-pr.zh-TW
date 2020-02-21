---
title: 'Lync Server 2013: （選用） 驗證電話撥入式會議設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing settings
ms:assetid: a85efdda-97b0-4f3b-bd26-04416bee8ef5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412789(v=OCS.15)
ms:contentKeyID: 48185027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ae67001d7e041cf0b4e8f6a01fb9278f3d79300
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-settings-in-lync-server-2013"></a><span data-ttu-id="a42ac-102">（選用）確認 Lync Server 2013 中的撥入式會議設定</span><span class="sxs-lookup"><span data-stu-id="a42ac-102">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a42ac-103">_**主題上次修改日期：** 2010年-11-02_</span><span class="sxs-lookup"><span data-stu-id="a42ac-103">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="a42ac-104">為您的撥入式會議組態的最終驗證，您可以搜尋有未由任何存取號碼撥入式會議地區的撥號對應表計劃，以及沒有制定撥入式會議地區的存取號碼。</span><span class="sxs-lookup"><span data-stu-id="a42ac-104">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region.</span></span> <span data-ttu-id="a42ac-105">此步驟是選用的。</span><span class="sxs-lookup"><span data-stu-id="a42ac-105">This step is optional.</span></span>

<div>

## <a name="to-find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="a42ac-106">若要尋找與未由任何存取號碼撥入式會議地區的撥號對應表計劃</span><span class="sxs-lookup"><span data-stu-id="a42ac-106">To find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1.  <span data-ttu-id="a42ac-107">以 RTCUniversalServerAdmins 群組成員或 **Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="a42ac-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="a42ac-108">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="a42ac-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a42ac-109">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a42ac-109">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    <span data-ttu-id="a42ac-110">此 cmdlet 會傳回所有具有不是由任何存取號碼撥入式會議地區的撥號對應表計劃。</span><span class="sxs-lookup"><span data-stu-id="a42ac-110">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>

</div>

<div>

## <a name="to-find-access-numbers-without-assigned-regions"></a><span data-ttu-id="a42ac-111">若要尋找沒有指派之地區的存取號碼</span><span class="sxs-lookup"><span data-stu-id="a42ac-111">To find access numbers without assigned regions</span></span>

1.  <span data-ttu-id="a42ac-112">以 RTCUniversalServerAdmins 群組成員或 **Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="a42ac-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="a42ac-113">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="a42ac-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a42ac-114">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a42ac-114">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    <span data-ttu-id="a42ac-115">此 cmdlet 會傳回與地區不相關的所有電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="a42ac-115">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

