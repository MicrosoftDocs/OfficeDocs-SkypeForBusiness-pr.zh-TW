---
title: Lync Server 2013： (選用) 驗證電話撥入式會議設定
description: Lync Server 2013： (選用) 驗證電話撥入式會議設定。
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
ms.openlocfilehash: ec002cfbd7cdd67498768a360143f88ab4f8e1b7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572559"
---
# <a name="optional-verify-dial-in-conferencing-settings-in-lync-server-2013"></a><span data-ttu-id="18d27-103"> (選用) 驗證 Lync Server 2013 中的電話撥入式會議設定</span><span class="sxs-lookup"><span data-stu-id="18d27-103">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18d27-104">_**主題上次修改日期：** 2010-11-02_</span><span class="sxs-lookup"><span data-stu-id="18d27-104">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="18d27-105">做為您的電話撥入式會議設定的最終驗證，您可以搜尋撥號對應表，該撥號對應表中的電話撥入式會議地區未使用任何存取號碼，且未指定電話撥入式會議區域的存取號碼。</span><span class="sxs-lookup"><span data-stu-id="18d27-105">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region.</span></span> <span data-ttu-id="18d27-106">這是選擇性的步驟。</span><span class="sxs-lookup"><span data-stu-id="18d27-106">This step is optional.</span></span>

<div>

## <a name="to-find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="18d27-107">使用電話撥入式會議地區未使用的存取號碼來尋找撥號對應表</span><span class="sxs-lookup"><span data-stu-id="18d27-107">To find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1.  <span data-ttu-id="18d27-108">以 RTCUniversalServerAdmins 群組成員或 **Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="18d27-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="18d27-109">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="18d27-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="18d27-110">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="18d27-110">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    <span data-ttu-id="18d27-111">此 Cmdlet 會傳回所有電話撥入式會議地區未由存取號碼使用的撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="18d27-111">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>

</div>

<div>

## <a name="to-find-access-numbers-without-assigned-regions"></a><span data-ttu-id="18d27-112">尋找未指派地區的存取號碼</span><span class="sxs-lookup"><span data-stu-id="18d27-112">To find access numbers without assigned regions</span></span>

1.  <span data-ttu-id="18d27-113">以 RTCUniversalServerAdmins 群組成員或 **Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="18d27-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="18d27-114">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="18d27-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="18d27-115">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="18d27-115">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    <span data-ttu-id="18d27-116">此 Cmdlet 會傳回與地區無關聯的所有電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="18d27-116">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

