---
title: Lync Server 2013： (選用) Modify DTMF 命令的按鍵對應
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7104a24c7bf02c310cb1deb7b8f9de3ad51407c9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524420"
---
# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a><span data-ttu-id="88e87-102"> (選用) 在 Lync Server 2013 中修改 DTMF 命令的按鍵對應</span><span class="sxs-lookup"><span data-stu-id="88e87-102">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88e87-103">_**主題上次修改日期：** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="88e87-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="88e87-104">電話撥入式會議使用者可按下電話按鍵上的按鍵，以執行雙音多頻率 (DTMF) 命令。</span><span class="sxs-lookup"><span data-stu-id="88e87-104">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands.</span></span> <span data-ttu-id="88e87-105">DTMF 命令可讓撥入會議的使用者控制會議設定 (例如，靜音和 unmuting 本身，或使用電話上的小鍵盤鎖定和解除鎖定會議) 。</span><span class="sxs-lookup"><span data-stu-id="88e87-105">DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> <span data-ttu-id="88e87-106">您可以使用 Cmdlet 來修改 DTMF 命令所使用的金鑰。</span><span class="sxs-lookup"><span data-stu-id="88e87-106">You can use cmdlets to modify the keys used for the DTMF commands.</span></span> <span data-ttu-id="88e87-107">這是選擇性的步驟。</span><span class="sxs-lookup"><span data-stu-id="88e87-107">This step is optional.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88e87-108">如需這些 Cmdlet 及可能的 DTMF 選項的詳細資訊，請參閱 Lync Server 管理命令介面檔或 Lync Server Management Shell 命令列說明。</span><span class="sxs-lookup"><span data-stu-id="88e87-108">For details about these cmdlets and the possible DTMF options, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="88e87-109">修改 DTMF 命令的按鍵對應</span><span class="sxs-lookup"><span data-stu-id="88e87-109">To modify the key mapping of DTMF commands</span></span>

1.  <span data-ttu-id="88e87-110">以 **RTCUniversalServerAdmins** 群組成員的身分，或是 **Cs-ServerAdministrator** 或 **CsAdministrator** 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="88e87-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="88e87-111">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="88e87-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="88e87-112">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="88e87-112">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingDtmfConfiguration
    
    <span data-ttu-id="88e87-113">此 Cmdlet 會傳回用於電話撥入式會議的 DTMF 設定。</span><span class="sxs-lookup"><span data-stu-id="88e87-113">This cmdlet returns the DTMF settings used for dial-in conferencing.</span></span>

4.  <span data-ttu-id="88e87-114">執行下列 Cmdlet，並指定要變更之每個選項的按鍵：</span><span class="sxs-lookup"><span data-stu-id="88e87-114">Run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    <span data-ttu-id="88e87-115">此 Cmdlet 會修改用於電話撥入式會議的 DTMF 設定。</span><span class="sxs-lookup"><span data-stu-id="88e87-115">This cmdlet modifies the DTMF settings used for dial-in conferencing.</span></span>
    
    <span data-ttu-id="88e87-116">例如：</span><span class="sxs-lookup"><span data-stu-id="88e87-116">For example:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    <span data-ttu-id="88e87-117">這個範例會將已按下的按鍵換用，以啟用或停用用來啟用或停用的宣告和按鍵，以靜音和取消靜音所有參與者。</span><span class="sxs-lookup"><span data-stu-id="88e87-117">This example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants.</span></span> <span data-ttu-id="88e87-118">因為未指定身分識別，所以這些變更會套用到全域 DTMF 設定。</span><span class="sxs-lookup"><span data-stu-id="88e87-118">Because no Identity is specified, these changes apply to the global DTMF settings.</span></span>

5.  <span data-ttu-id="88e87-119"> (選用) 若要為特定網站建立其他 DTMF 命令集，請使用具有網站身分識別的 **set-csdialinconferencingdtmfconfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="88e87-119">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span> <span data-ttu-id="88e87-120">當您為網站建立新的 DTMF 設定時，網站設定會優先于通用設定。</span><span class="sxs-lookup"><span data-stu-id="88e87-120">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="88e87-121">如需詳細資訊，請參閱 Lync Server 管理命令介面檔或 Lync Server Management Shell 命令列說明。</span><span class="sxs-lookup"><span data-stu-id="88e87-121">For details, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

