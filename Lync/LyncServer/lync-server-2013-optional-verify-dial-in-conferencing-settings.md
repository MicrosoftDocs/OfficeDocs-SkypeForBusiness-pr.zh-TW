---
title: Lync Server 2013：(選用) 驗證電話撥入式會議設定
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
ms.openlocfilehash: dd283e8d7b86fbadfb2c23b0e8cbe2dc22b66cce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-settings-in-lync-server-2013"></a><span data-ttu-id="813e3-102">(選用) 在 Lync Server 2013 中驗證電話撥入式會議設定</span><span class="sxs-lookup"><span data-stu-id="813e3-102">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="813e3-103">_**主題上次修改日期：** 2010-11-02_</span><span class="sxs-lookup"><span data-stu-id="813e3-103">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="813e3-104">針對您的電話撥入式會議設定的最終驗證，您可以搜尋其電話撥入式會議區域不是由任何存取號碼所使用的撥號方案，以及尚未指定電話撥入式會議區域的存取號碼。</span><span class="sxs-lookup"><span data-stu-id="813e3-104">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region.</span></span> <span data-ttu-id="813e3-105">此為選用步驟。</span><span class="sxs-lookup"><span data-stu-id="813e3-105">This step is optional.</span></span>

<div>

## <a name="to-find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="813e3-106">若要尋找電話撥入式會議區域中的撥號方案（不是由存取號碼使用）</span><span class="sxs-lookup"><span data-stu-id="813e3-106">To find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1.  <span data-ttu-id="813e3-107">以 RTCUniversalServerAdmins 群組的成員或**Cs-ServerAdministrator**或**CsAdministrator**角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="813e3-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="813e3-108">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="813e3-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="813e3-109">在命令提示字元執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="813e3-109">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    <span data-ttu-id="813e3-110">這個 Cmdlet 會傳回具有電話撥入式會議區域的所有撥號方案，這些方案不是由存取號碼所使用。</span><span class="sxs-lookup"><span data-stu-id="813e3-110">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>

</div>

<div>

## <a name="to-find-access-numbers-without-assigned-regions"></a><span data-ttu-id="813e3-111">若要尋找沒有指定區域的存取號碼</span><span class="sxs-lookup"><span data-stu-id="813e3-111">To find access numbers without assigned regions</span></span>

1.  <span data-ttu-id="813e3-112">以 RTCUniversalServerAdmins 群組的成員或**Cs-ServerAdministrator**或**CsAdministrator**角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="813e3-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="813e3-113">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="813e3-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="813e3-114">在命令提示字元執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="813e3-114">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    <span data-ttu-id="813e3-115">這個 Cmdlet 會傳回與區域不相關的所有電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="813e3-115">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

