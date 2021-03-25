---
title: 規劃在內部和外部關閉舊版驗證方法
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: 本文概述的 Cmdlet 可讓系統管理員更深入地控制企業內部及外部使用的驗證方法。 管理員可以在內部或外部開啟或關閉驗證方法。
ms.openlocfilehash: 3d7217167f7e72c4db0ec438fb20d746cd612cc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116051"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a><span data-ttu-id="0e936-104">規劃在內部和外部關閉舊版驗證方法。</span><span class="sxs-lookup"><span data-stu-id="0e936-104">Planning to turn off Legacy authentication methods internally and externally to your network.</span></span>

> [!NOTE]
> <span data-ttu-id="0e936-105">如果您即將閱讀本文，您應該已經知道支援的新式驗證拓撲、ADAL 和關於新式驗證設定，但是如果您不想這麼做，請參閱以下所需的文章：</span><span class="sxs-lookup"><span data-stu-id="0e936-105">If you're about to read this article, you should already know about supported Modern Authentication topologies, ADAL, and about Modern Authentication config, but, in case you don't, here are the articles you need to start out:</span></span> 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](./topologies-supported.md)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](/skypeforbusiness/manage/authentication/use-adal)
  
<span data-ttu-id="0e936-106">新式驗證不只是啟用更安全的驗證方法，例如 Two-Factor 驗證或以憑證為基礎的驗證，只要不需要使用者名稱或密碼，就能對您的使用者執行授權。</span><span class="sxs-lookup"><span data-stu-id="0e936-106">Modern Authentication doesn't just enable more secure methods of authentication, like Two-Factor Auth, or Certificate-based Auth, it can carry out authorization of your user without needing a username or password too.</span></span> <span data-ttu-id="0e936-107">這十分實用。</span><span class="sxs-lookup"><span data-stu-id="0e936-107">It's pretty handy.</span></span>

<span data-ttu-id="0e936-108">本文將協助您插入已受到拒絕服務 (DOS) 攻擊的漏洞，方法是將用於驗證的舊方法（從外部、內部或兩者）關閉至您的網路。</span><span class="sxs-lookup"><span data-stu-id="0e936-108">This article will help you plug holes that have been exploited for Denial Of Service (DOS) attacks on Skype for Business Servers, by turning off older methods used for authentication, externally, internally, or both, to your network.</span></span> <span data-ttu-id="0e936-109">例如，協助停用 DOS 攻擊的一個好方法是關閉 Windows 整合式驗證 (，其中包括 NTLM 和 Kerberos) 。</span><span class="sxs-lookup"><span data-stu-id="0e936-109">For example, one good method to help stop DOS attacks would be to turn off Windows Integrated Authentication (which includes NTLM and Kerberos).</span></span> <span data-ttu-id="0e936-110">從外部關閉 NTLM 並依賴憑證型驗證，可協助保護密碼不會洩密。</span><span class="sxs-lookup"><span data-stu-id="0e936-110">Turning off NTLM externally and relying on certificate-based authentication helps to protect passwords from exposure.</span></span> <span data-ttu-id="0e936-111">這是因為 NTLM 會使用密碼認證來驗證使用者，但是由新式驗證啟用憑證型驗證--不是。</span><span class="sxs-lookup"><span data-stu-id="0e936-111">This is because NTLM uses password credentials to authenticate users, but certificate-based authentication -- enabled by Modern Auth -- doesn't.</span></span> <span data-ttu-id="0e936-112">這表示降低 DOS 攻擊的一個理想選擇是在外部封鎖 NTLM，而只在這裡使用憑證型驗證。</span><span class="sxs-lookup"><span data-stu-id="0e936-112">That means one ideal option to reduce DOS attacks is to block NTLM externally, and use only certificate-based authentication there, instead.</span></span>

<span data-ttu-id="0e936-113">完全正確，讓我們開始吧。</span><span class="sxs-lookup"><span data-stu-id="0e936-113">All right, let's get started.</span></span>

## <a name="what-would-you-be-changing"></a><span data-ttu-id="0e936-114">您要變更什麼？</span><span class="sxs-lookup"><span data-stu-id="0e936-114">What would you be changing?</span></span> 

<span data-ttu-id="0e936-115">這些 Cmdlet 適用于存取的 SIP 和 Web 服務點。</span><span class="sxs-lookup"><span data-stu-id="0e936-115">These cmdlets work for both SIP and Web Services points of access.</span></span> <span data-ttu-id="0e936-116">雖然這兩個通道使用不同的存取方法，執行從 NTLM 和 Kerberos 到匿名存取的情況，但已考慮商務用 Skype 所使用的所有標準方法。</span><span class="sxs-lookup"><span data-stu-id="0e936-116">Though these two channels use different access methods, running the gamut from NTLM and Kerberos to Anonymous access, all standard methods used by Skype for Business have been taken into consideration.</span></span>

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a><span data-ttu-id="0e936-117">如何取得 Get 及 Set-CsAuthConfig Cmdlet</span><span class="sxs-lookup"><span data-stu-id="0e936-117">How to get the Get- and Set-CsAuthConfig cmdlets</span></span>

<span data-ttu-id="0e936-118">這些指令程式將只會在2018年7月 (的商務用 Skype Server 2015 中安裝後置中的「累計更新」) ，然後您就可以為您的商務用 Skype 伺服器展開多種拓撲。</span><span class="sxs-lookup"><span data-stu-id="0e936-118">These cmdlets will only be installed post July 2018 cumulative update (6.0.9319.534) for Microsoft Skype for Business Server 2015, and then you have a variety of topologies that can be rolled out for your Skype for Business server.</span></span>

## <a name="topologies"></a><span data-ttu-id="0e936-119">拓撲</span><span class="sxs-lookup"><span data-stu-id="0e936-119">Topologies</span></span>

<span data-ttu-id="0e936-120">請務必記住，此案例中包含的支援拓撲是必要的！</span><span class="sxs-lookup"><span data-stu-id="0e936-120">It's important to keep in mind that these are the Supported Topologies involved in this scenario!</span></span> <span data-ttu-id="0e936-121">例如，如果您需要尋求協助，以協助封鎖方法，您必須在下列類型之間進行設定。</span><span class="sxs-lookup"><span data-stu-id="0e936-121">If you need to go to Support for help with blocking a method, for example, you will need to have a configuration among the types below.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="0e936-122">在下清單格和描述中， *新式驗證* 是以 __MA__ 為縮寫，而 *Windows 整合式驗證* 是一種 __入選__。</span><span class="sxs-lookup"><span data-stu-id="0e936-122">In the table and descriptions below, *Modern Authentication* is abbreviated as __MA__ and *Windows Integrated Authentication* is abbreviated as __Win__.</span></span> <span data-ttu-id="0e936-123">如提醒，Windows 整合式驗證是由兩個方法組成： NTLM 和 Kerberos 驗證。</span><span class="sxs-lookup"><span data-stu-id="0e936-123">As a reminder, Windows Integrated Authentication is made up of two methods: NTLM and Kerberos authentication.</span></span> <span data-ttu-id="0e936-124">您將需要知道這一點才能正確讀取資料表！</span><span class="sxs-lookup"><span data-stu-id="0e936-124">You'll need to know this to read the table properly!</span></span>


|       |<span data-ttu-id="0e936-125">外部</span><span class="sxs-lookup"><span data-stu-id="0e936-125">Externally</span></span>  |<span data-ttu-id="0e936-126">內部</span><span class="sxs-lookup"><span data-stu-id="0e936-126">Internally</span></span>  |<span data-ttu-id="0e936-127">參數</span><span class="sxs-lookup"><span data-stu-id="0e936-127">Parameter</span></span>  |
|---------|:---------|:---------|---------|
|<span data-ttu-id="0e936-128">__Type 1__</span><span class="sxs-lookup"><span data-stu-id="0e936-128">__Type 1__</span></span>   |  <span data-ttu-id="0e936-129">MA + Win</span><span class="sxs-lookup"><span data-stu-id="0e936-129">MA + Win</span></span>       | <span data-ttu-id="0e936-130">MA + Win</span><span class="sxs-lookup"><span data-stu-id="0e936-130">MA + Win</span></span>         |  <span data-ttu-id="0e936-131">AllowAllExternallyAndInternally</span><span class="sxs-lookup"><span data-stu-id="0e936-131">AllowAllExternallyAndInternally</span></span>       |
|<span data-ttu-id="0e936-132">__類型2__</span><span class="sxs-lookup"><span data-stu-id="0e936-132">__Type 2__</span></span>   |  <span data-ttu-id="0e936-133">馬</span><span class="sxs-lookup"><span data-stu-id="0e936-133">MA</span></span>       | <span data-ttu-id="0e936-134">MA + Win</span><span class="sxs-lookup"><span data-stu-id="0e936-134">MA + Win</span></span>         | <span data-ttu-id="0e936-135">BlockWindowsAuthExternally</span><span class="sxs-lookup"><span data-stu-id="0e936-135">BlockWindowsAuthExternally</span></span>        |
|<span data-ttu-id="0e936-136">__類型3__</span><span class="sxs-lookup"><span data-stu-id="0e936-136">__Type 3__</span></span>   |  <span data-ttu-id="0e936-137">馬</span><span class="sxs-lookup"><span data-stu-id="0e936-137">MA</span></span>       | <span data-ttu-id="0e936-138">馬</span><span class="sxs-lookup"><span data-stu-id="0e936-138">MA</span></span>        | <span data-ttu-id="0e936-139">BlockWindowsAuthExternallyAndInternally</span><span class="sxs-lookup"><span data-stu-id="0e936-139">BlockWindowsAuthExternallyAndInternally</span></span>        |
|<span data-ttu-id="0e936-140">__類型4__</span><span class="sxs-lookup"><span data-stu-id="0e936-140">__Type 4__</span></span>   |  <span data-ttu-id="0e936-141">馬</span><span class="sxs-lookup"><span data-stu-id="0e936-141">MA</span></span>       | <span data-ttu-id="0e936-142">贏得</span><span class="sxs-lookup"><span data-stu-id="0e936-142">Win</span></span>        | <span data-ttu-id="0e936-143">BlockWindowsAuthExternallyAndModernAuthInternally</span><span class="sxs-lookup"><span data-stu-id="0e936-143">BlockWindowsAuthExternallyAndModernAuthInternally</span></span>    |
|<span data-ttu-id="0e936-144">__類型5__</span><span class="sxs-lookup"><span data-stu-id="0e936-144">__Type 5__</span></span>   |  <span data-ttu-id="0e936-145">MA + Win</span><span class="sxs-lookup"><span data-stu-id="0e936-145">MA + Win</span></span>       | <span data-ttu-id="0e936-146">贏得</span><span class="sxs-lookup"><span data-stu-id="0e936-146">Win</span></span>        | <span data-ttu-id="0e936-147">BlockModernAuthInternally</span><span class="sxs-lookup"><span data-stu-id="0e936-147">BlockModernAuthInternally</span></span>         |

<span data-ttu-id="0e936-148">__類型1描述：__ 此為商務用 Skype __Server 的 MA 開啟時__ 的預設案例。</span><span class="sxs-lookup"><span data-stu-id="0e936-148">__Type 1 Description:__ This is the default scenario when MA is turned __on__ for Skype for Business Server.</span></span> <span data-ttu-id="0e936-149">換句話說，這是設定 MA 的 *起始點* 。</span><span class="sxs-lookup"><span data-stu-id="0e936-149">In other words, this is the *starting point* when MA is configured.</span></span>

<span data-ttu-id="0e936-150">__Type 2 Description：__ 此拓撲會在 *外部* 封鎖 ntlm，但是允許不支援 ADAL) 之用戶端的 Ntlm 或 Kerberos (*在內部* 運作。</span><span class="sxs-lookup"><span data-stu-id="0e936-150">__Type 2 Description:__ This topology blocks NTLM *externally*, but allows NTLM or Kerberos (for clients that don't support ADAL) to work *internally*.</span></span> <span data-ttu-id="0e936-151">如果您的用戶端支援 ADAL，他們會在內部使用 MA。</span><span class="sxs-lookup"><span data-stu-id="0e936-151">If your clients  do support ADAL they will use MA internally.</span></span>

<span data-ttu-id="0e936-152">__類型3描述：__ 此拓撲要求所有使用者 MA。</span><span class="sxs-lookup"><span data-stu-id="0e936-152">__Type 3 Description:__ This topology requires MA for all users.</span></span> <span data-ttu-id="0e936-153">所有支援 ADAL 功能的用戶端都會在此拓撲中運作，而不會利用密碼（例如，您關閉使用以憑證為基礎的驗證）。</span><span class="sxs-lookup"><span data-stu-id="0e936-153">All your ADAL-capable clients will work in this topology, and passwords will not be leveraged if, for example, you turn off the use of passwords with Certificate-based Auth.</span></span>

<span data-ttu-id="0e936-154">__類型4描述：__ 此拓撲會在內部 *從外部* 封鎖 NTLM，並在內部封鎖 MA。</span><span class="sxs-lookup"><span data-stu-id="0e936-154">__Type 4 Description:__ This topology blocks NTLM *externally* and MA internally.</span></span> <span data-ttu-id="0e936-155">它可讓 *所有用戶端\*\*在內部* 使用舊版驗證方法， (甚至具備 ADAL 功能的用戶端) 。</span><span class="sxs-lookup"><span data-stu-id="0e936-155">It allows *all clients* to use legacy authentication methods *internally* (even ADAL-capable clients).</span></span>

<span data-ttu-id="0e936-156">__Type 5 Description：__ *對外*，您的現代 ADAL 用戶端將使用 MA，任何不支援 ADAL 的用戶端都會使用舊版驗證方法。</span><span class="sxs-lookup"><span data-stu-id="0e936-156">__Type 5 Description:__ *Externally*, your modern ADAL clients will use MA and any clients that don't support ADAL will use legacy authentication methods.</span></span> <span data-ttu-id="0e936-157">不過， *在內部*， *所有用戶端* 都會使用舊版驗證 (包括所有支援 ADAL 功能的用戶端) 。</span><span class="sxs-lookup"><span data-stu-id="0e936-157">But, *internally* *all clients* will use legacy authentication (including all ADAL-capable clients).</span></span>

<span data-ttu-id="0e936-158">在可用選項中追蹤密碼保護的目的相當簡單。</span><span class="sxs-lookup"><span data-stu-id="0e936-158">It's pretty easy to lose track of the goal of protecting your passwords in the options available.</span></span> <span data-ttu-id="0e936-159">請記住，理想的情況是使用 MA 外部 (例如，透過設定憑證型驗證) ，避免 DOS 攻擊。</span><span class="sxs-lookup"><span data-stu-id="0e936-159">Keep in mind the ideal situation is to use MA externally (for example, by configuring certificate-based auth), to avoid DOS attacks.</span></span> <span data-ttu-id="0e936-160">如果您是在您的現代用戶端內部利用這種方式，您也會進一步對您的網路進行商務用 Skype Server DOS 攻擊的考驗。</span><span class="sxs-lookup"><span data-stu-id="0e936-160">If you leverage it internally for your modern clients, you'll also future-proof your network regarding Skype for Business Server DOS attacks.</span></span>

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a><span data-ttu-id="0e936-161">在全域層級使用 Set-CsAuthConfig 的原因</span><span class="sxs-lookup"><span data-stu-id="0e936-161">Why to use Set-CsAuthConfig at the Global level</span></span>

<span data-ttu-id="0e936-162">`Set-CsAuthConfig`註冊機構和 Web 服務角色上的指令 Cmdlet 效果設定。</span><span class="sxs-lookup"><span data-stu-id="0e936-162">The `Set-CsAuthConfig` cmdlet effects configuration on both the Registrar and the Web Services roles.</span></span>

<span data-ttu-id="0e936-163">此 Cmdlet 應該在您的商務用 Skype 伺服器的全域層級執行。</span><span class="sxs-lookup"><span data-stu-id="0e936-163">This cmdlet is meant to be run at the Global level of your Skype for Business server.</span></span> <span data-ttu-id="0e936-164">它 *可以* 在集區層級執行，但 *不建議使用* ，因為這會增加安裝的複雜性。</span><span class="sxs-lookup"><span data-stu-id="0e936-164">It *can* be run at the Pool level but that is *not recommended* because it will add complexity to your installation.</span></span> <span data-ttu-id="0e936-165">在集區層級執行下列命令，如果您的集區沒有所有的角色包含 (例如，它沒有) 的 Web 服務，將只會針對註冊機構角色設定設定。</span><span class="sxs-lookup"><span data-stu-id="0e936-165">By running these commands at the Pool level, if your Pool doesn't have all of the roles included (for example, it doesn't have Web Services), the settings will only be set for the Registrar role.</span></span> <span data-ttu-id="0e936-166">在此情況下，Web 服務會使用來自全域層級的設定，這可能是令人困惑的行為 (尤其是在無意中) 時執行。</span><span class="sxs-lookup"><span data-stu-id="0e936-166">In that case, Web Services will carry on with settings from the Global level, which can be confusing behaviour (particularly when this is done unintentionally).</span></span>

<span data-ttu-id="0e936-167">如果用戶端使用來自某個集區的註冊器設定，以及另一個集區的 Web 服務設定，且驗證設定處於不一致的狀態，yous 用戶端可能無法登入。</span><span class="sxs-lookup"><span data-stu-id="0e936-167">If a client uses the Registrar settings from one pool and the Web Services settings from another pool and the authentication settings are in an inconsistent state, yous clients may be unable to log on.</span></span>

<span data-ttu-id="0e936-168">此外，如果集區只有一個角色存在：</span><span class="sxs-lookup"><span data-stu-id="0e936-168">Also, if there's only one role present for a pool:</span></span> 
* <span data-ttu-id="0e936-169">Set-只會設定對應至存在之角色的設定。</span><span class="sxs-lookup"><span data-stu-id="0e936-169">Set- will only set the settings that correspond to the role that exists.</span></span> <span data-ttu-id="0e936-170">因為 *未* 設定某些設定，所以不會提供任何特殊的警告。</span><span class="sxs-lookup"><span data-stu-id="0e936-170">No special warning will be given because some settings were *not* set.</span></span> 
* <span data-ttu-id="0e936-171">Get-會傳回對應至存在之角色的設定，以及不存在之角色的全域設定。</span><span class="sxs-lookup"><span data-stu-id="0e936-171">Get- will return the setting that corresponds to the role that exists, and the Global settings for the role that doesn't exist.</span></span>
* <span data-ttu-id="0e936-172">如果集區的角色都不存在，則無論是 Set 和 Get，都將會傳回錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="0e936-172">If neither role is present for a pool, both Set- and Get- will return an error message.</span></span>
* <span data-ttu-id="0e936-173">如果集區的兩個角色都存在，但沒有在集區層級定義原則，則 Get 會傳回錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="0e936-173">If both roles are present for a pool but policies aren't defined at the pool level, Get- will return an error message.</span></span>

<span data-ttu-id="0e936-174">它可能會 wisest，以取得這些值，並在進行任何變更之前，以螢幕擷取畫面或記錄其開始狀態。</span><span class="sxs-lookup"><span data-stu-id="0e936-174">It may be wisest to do a Get- for these values, and to screenshot or record their starting state before making any changes.</span></span> <span data-ttu-id="0e936-175">您也可以考慮保留 OneNote 中的變更記錄。</span><span class="sxs-lookup"><span data-stu-id="0e936-175">You might also consider keeping a log of changes in a OneNote.</span></span>

> [!NOTE]
> 
> <span data-ttu-id="0e936-176">附注：設定 CsAuthConfig 後，您必須在每一部電腦上執行 Enable-CsComputer，使設定生效。</span><span class="sxs-lookup"><span data-stu-id="0e936-176">Note: After configuring the CsAuthConfig, you must run Enable-CsComputer on each computer in order for the settings to take effect.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0e936-177">如果您使用的是 Lync Web Access (LWA) ，且必須使用以表單為基礎的 Access (FBA) 以進行外部存取，請重新設定 LWA，讓用戶端可以透過匿名存取來存取，以支援這些案例。</span><span class="sxs-lookup"><span data-stu-id="0e936-177">If you're using Lync Web Access (LWA) and must use Forms-based Access (FBA) for external access, reconfigure LWA so that clients can access it with Anonymous Access to support these scenarios.</span></span> <span data-ttu-id="0e936-178">同樣地，如果您使用電話撥入式 Pin 碼，將只會封鎖外部使用者的 FBA。</span><span class="sxs-lookup"><span data-stu-id="0e936-178">Likewise, if you use Dial-in Pin, FBA will be blocked for external users only.</span></span> <span data-ttu-id="0e936-179">如果他們需要變更其 pin 碼，則必須在內部登入他們的公司以執行此動作。</span><span class="sxs-lookup"><span data-stu-id="0e936-179">If they need to change their pin, they will need to login to their corporation to do so, internally.</span></span>

> [!NOTE]
> 
> <span data-ttu-id="0e936-180">如果您使用 BlockWindowsAuthExternally 參數對外封鎖 NTLM，請注意，這也會在內部為 SIP 通道封鎖 NTLM。</span><span class="sxs-lookup"><span data-stu-id="0e936-180">If you use the BlockWindowsAuthExternally parameter to externally block NTLM, be aware this also blocks NTLM internally for the SIP channel.</span></span> <span data-ttu-id="0e936-181">不過，版本高於2010的商務用 Skype 和 Lync 用戶端仍可登入，因為他們會使用 NTLM over HTTP 登入，並在內部登入，然後取得憑證以透過 SIP 登入。</span><span class="sxs-lookup"><span data-stu-id="0e936-181">However, Skype for Business and Lync clients newer than 2010 will still be able to login because they will use NTLM over HTTP for signin, internally, and then fetch a certificate to login over SIP.</span></span> <span data-ttu-id="0e936-182">不過，低於2010的用戶端在此情況下將無法在內部登入，而且您可能想要考慮升級這些應用程式，讓使用者能夠繼續安全運作。</span><span class="sxs-lookup"><span data-stu-id="0e936-182">However, clients older than 2010 will not be able to login internally in this circumstance, and you may want to consider upgrading these applications so that your users can resume secure functionality.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="0e936-183">部分商務用 Skype web 應用程式不支援 MA。</span><span class="sxs-lookup"><span data-stu-id="0e936-183">Some of the Skype for Business web applications don't support MA.</span></span> <span data-ttu-id="0e936-184">所以，使用 BlockWindowsAuthExternallyAndInternally 案例時，您將無法存取這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="0e936-184">So by using the BlockWindowsAuthExternallyAndInternally scenario, you won't be able to access these applications.</span></span> <span data-ttu-id="0e936-185">沒有 MA 支援的應用程式是 Web 排程器、Dial-In 頁面、商務用 Skype 控制台 (CSCP) 和回應群組設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="0e936-185">Applications without MA support are Web Scheduler, Dial-In Page, Skype for Business Control Panel (CSCP), and Response Group Settings Page.</span></span> 

## <a name="links"></a><span data-ttu-id="0e936-186">連結</span><span class="sxs-lookup"><span data-stu-id="0e936-186">Links</span></span> 
- <span data-ttu-id="0e936-187">如需詳細 PowerShell 資訊：</span><span class="sxs-lookup"><span data-stu-id="0e936-187">For more PowerShell information:</span></span>
    -  [<span data-ttu-id="0e936-188">CsAuthConfig</span><span class="sxs-lookup"><span data-stu-id="0e936-188">Get-CsAuthConfig</span></span>](/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [<span data-ttu-id="0e936-189">CsAuthConfig</span><span class="sxs-lookup"><span data-stu-id="0e936-189">Set-CsAuthConfig</span></span>](/powershell/module/skype/set-csauthconfig?view=skype-ps)

- <span data-ttu-id="0e936-190">如需如何使用命令或執行安裝所需之 CU 的相關指導：</span><span class="sxs-lookup"><span data-stu-id="0e936-190">For more direction on how to use the commands or on the CU needed to install them:</span></span>
    - [<span data-ttu-id="0e936-191">Cmdlet 簡報</span><span class="sxs-lookup"><span data-stu-id="0e936-191">Cmdlets briefing</span></span>](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - <span data-ttu-id="0e936-192">[商務用 Skype Server 2015 的更新](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) (一般) </span><span class="sxs-lookup"><span data-stu-id="0e936-192">[Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) (General)</span></span>
    - <span data-ttu-id="0e936-193">[2018 年7月日的商務用 Skype Server 2015，核心元件 CU](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534) </span><span class="sxs-lookup"><span data-stu-id="0e936-193">The [July 2018 Skype for Business Server 2015, Core Components CU](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)</span></span>


