---
title: 'DTMF 命令的 Lync Server 2013: （選用） 修改按鍵對應'
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
ms.openlocfilehash: dcf6f6b2dd65d9429bf23397baff5bbe072800f0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a><span data-ttu-id="24c31-102">（選用）修改 Lync Server 2013 中的 DTMF 命令的按鍵對應</span><span class="sxs-lookup"><span data-stu-id="24c31-102">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24c31-103">_**主題上次修改日期：** 2012年-09-30_</span><span class="sxs-lookup"><span data-stu-id="24c31-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="24c31-104">電話撥入式會議使用者可以執行雙音多頻 (DTMF) 命令電話鍵台上按下機碼。</span><span class="sxs-lookup"><span data-stu-id="24c31-104">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands.</span></span> <span data-ttu-id="24c31-105">DTMF 命令可讓使用者撥入會議使用其電話按鍵來控制會議設定 （例如靜音和解除靜音本身或鎖定及解除鎖定會議）。</span><span class="sxs-lookup"><span data-stu-id="24c31-105">DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> <span data-ttu-id="24c31-106">您可以使用 cmdlet 來修改 DTMF 命令所使用的機碼。</span><span class="sxs-lookup"><span data-stu-id="24c31-106">You can use cmdlets to modify the keys used for the DTMF commands.</span></span> <span data-ttu-id="24c31-107">此步驟是選用的。</span><span class="sxs-lookup"><span data-stu-id="24c31-107">This step is optional.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="24c31-108">如需這些 cmdlet 及可用 DTMF 選項的詳細資訊，請參閱 Lync Server 管理命令介面文件或 Lync Server 管理命令介面命令列說明。</span><span class="sxs-lookup"><span data-stu-id="24c31-108">For details about these cmdlets and the possible DTMF options, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="24c31-109">若要修改 DTMF 命令的按鍵對應</span><span class="sxs-lookup"><span data-stu-id="24c31-109">To modify the key mapping of DTMF commands</span></span>

1.  <span data-ttu-id="24c31-110">**以 RTCUniversalServerAdmins**群組成員或**Cs-serveradministrator**或**CsAdministrator**角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="24c31-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="24c31-111">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="24c31-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="24c31-112">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="24c31-112">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingDtmfConfiguration
    
    <span data-ttu-id="24c31-113">此 cmdlet 會傳回用於撥入式會議的 DTMF 設定。</span><span class="sxs-lookup"><span data-stu-id="24c31-113">This cmdlet returns the DTMF settings used for dial-in conferencing.</span></span>

4.  <span data-ttu-id="24c31-114">執行下列 cmdlet，並指定要按下您想要變更每個選項的機碼：</span><span class="sxs-lookup"><span data-stu-id="24c31-114">Run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    <span data-ttu-id="24c31-115">此 cmdlet 會修改用於電話撥入式會議的 DTMF 設定。</span><span class="sxs-lookup"><span data-stu-id="24c31-115">This cmdlet modifies the DTMF settings used for dial-in conferencing.</span></span>
    
    <span data-ttu-id="24c31-116">例如：</span><span class="sxs-lookup"><span data-stu-id="24c31-116">For example:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    <span data-ttu-id="24c31-117">此範例可以互換按下啟用或停用宣告並按下靜音和取消靜音所有參與者的索引鍵的索引鍵。</span><span class="sxs-lookup"><span data-stu-id="24c31-117">This example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants.</span></span> <span data-ttu-id="24c31-118">因為指定沒有 Identity，則這些變更會套用至全域 DTMF 設定。</span><span class="sxs-lookup"><span data-stu-id="24c31-118">Because no Identity is specified, these changes apply to the global DTMF settings.</span></span>

5.  <span data-ttu-id="24c31-119">（選用）若要建立 DTMF 命令的特定網站的其他設定，請使用**New CsDialinConferencingDtmfConfiguration**指令程式與網站身分識別。</span><span class="sxs-lookup"><span data-stu-id="24c31-119">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span> <span data-ttu-id="24c31-120">當您建立新網站的 DTMF 設定時，網站設定優先於全域設定。</span><span class="sxs-lookup"><span data-stu-id="24c31-120">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="24c31-121">如需詳細資訊，請參閱 Lync Server 管理命令介面文件或 Lync Server 管理命令介面命令列說明。</span><span class="sxs-lookup"><span data-stu-id="24c31-121">For details, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

