---
title: 規劃在內部和外部將舊版驗證方法關閉至您的網路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: 本文概述可讓系統管理員進一步控制企業內部和外部使用之驗證方法的 Cmdlet。 系統管理員可以在內部或外部開啟或關閉驗證方法, 或從外部關閉驗證方法。
ms.openlocfilehash: aaee46b04832cc114f895f905c180fe089d7349d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192974"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a><span data-ttu-id="4deea-104">規劃在內部和外部將舊版驗證方法關閉至您的網路。</span><span class="sxs-lookup"><span data-stu-id="4deea-104">Planning to turn off Legacy authentication methods internally and externally to your network.</span></span>

> [!NOTE]
> <span data-ttu-id="4deea-105">如果您要閱讀本文, 您應該已經知道支援的新式驗證拓撲、ADAL, 以及關於新式驗證配置, 但如果您不這麼做, 以下是您需要開始的文章:</span><span class="sxs-lookup"><span data-stu-id="4deea-105">If you're about to read this article, you should already know about supported Modern Authentication topologies, ADAL, and about Modern Authentication config, but, in case you don't, here are the articles you need to start out:</span></span> 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
<span data-ttu-id="4deea-106">新式驗證並不只是啟用更安全的驗證方法 (例如雙因素驗證, 或以證書為基礎的驗證), 只要不需要使用者名稱或密碼, 就能自行執行您的使用者授權。</span><span class="sxs-lookup"><span data-stu-id="4deea-106">Modern Authentication doesn't just enable more secure methods of authentication, like Two-Factor Auth, or Certificate-based Auth, it can carry out authorization of your user without needing a username or password too.</span></span> <span data-ttu-id="4deea-107">這相當簡單。</span><span class="sxs-lookup"><span data-stu-id="4deea-107">It's pretty handy.</span></span>

<span data-ttu-id="4deea-108">本文將協助您插入在商務用 Skype 伺服器上受到拒絕服務 (DOS) 攻擊的漏洞, 方法是關閉針對您的網路進行驗證所使用的較舊的方法。</span><span class="sxs-lookup"><span data-stu-id="4deea-108">This article will help you plug holes that have been exploited for Denial Of Service (DOS) attacks on Skype for Business Servers, by turning off older methods used for authentication, externally, internally, or both, to your network.</span></span> <span data-ttu-id="4deea-109">例如, 協助停止 DOS 攻擊的一個好方法就是關閉 Windows 整合驗證 (包括 NTLM 與 Kerberos)。</span><span class="sxs-lookup"><span data-stu-id="4deea-109">For example, one good method to help stop DOS attacks would be to turn off Windows Integrated Authentication (which includes NTLM and Kerberos).</span></span> <span data-ttu-id="4deea-110">在外部關閉 NTLM 並依賴憑證式驗證可協助保護密碼免遭洩密。</span><span class="sxs-lookup"><span data-stu-id="4deea-110">Turning off NTLM externally and relying on certificate-based authentication helps to protect passwords from exposure.</span></span> <span data-ttu-id="4deea-111">這是因為 NTLM 使用密碼認證來驗證使用者, 但認證驗證 (由新式驗證所啟用) 不是。</span><span class="sxs-lookup"><span data-stu-id="4deea-111">This is because NTLM uses password credentials to authenticate users, but certificate-based authentication -- enabled by Modern Auth -- doesn't.</span></span> <span data-ttu-id="4deea-112">這表示減少 DOS 攻擊的一個理想選擇就是封鎖外部的 NTLM, 並改為在這裡使用憑證式驗證。</span><span class="sxs-lookup"><span data-stu-id="4deea-112">That means one ideal option to reduce DOS attacks is to block NTLM externally, and use only certificate-based authentication there, instead.</span></span>

<span data-ttu-id="4deea-113">完全正確, 讓我們開始吧。</span><span class="sxs-lookup"><span data-stu-id="4deea-113">All right, let's get started.</span></span>

## <a name="what-would-you-be-changing"></a><span data-ttu-id="4deea-114">您要變更什麼？</span><span class="sxs-lookup"><span data-stu-id="4deea-114">What would you be changing?</span></span> 

<span data-ttu-id="4deea-115">這些 Cmdlet 適用于 SIP 和 Web 服務存取點。</span><span class="sxs-lookup"><span data-stu-id="4deea-115">These cmdlets work for both SIP and Web Services points of access.</span></span> <span data-ttu-id="4deea-116">雖然這兩個通道使用不同的存取方法, 請執行從 NTLM 與 Kerberos 到匿名存取的 gamut, 否則已考慮商務用 Skype 所使用的所有標準方法。</span><span class="sxs-lookup"><span data-stu-id="4deea-116">Though these two channels use different access methods, running the gamut from NTLM and Kerberos to Anonymous access, all standard methods used by Skype for Business have been taken into consideration.</span></span>

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a><span data-ttu-id="4deea-117">如何取得 CsAuthConfig 和設定的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="4deea-117">How to get the Get- and Set-CsAuthConfig cmdlets</span></span>

<span data-ttu-id="4deea-118">這些 Cmdlet 只會安裝在 Microsoft 商務用 Skype Server 2015 的2018年7月的累加更新 (6.0.9319.534) 之後, 您就可以針對您的商務用 Skype 伺服器推出多種不同的拓撲。</span><span class="sxs-lookup"><span data-stu-id="4deea-118">These cmdlets will only be installed post July 2018 cumulative update (6.0.9319.534) for Microsoft Skype for Business Server 2015, and then you have a variety of topologies that can be rolled out for your Skype for Business server.</span></span>

## <a name="topologies"></a><span data-ttu-id="4deea-119">形</span><span class="sxs-lookup"><span data-stu-id="4deea-119">Topologies</span></span>

<span data-ttu-id="4deea-120">請務必記住, 這種情況下會涉及以下所支援的拓撲!</span><span class="sxs-lookup"><span data-stu-id="4deea-120">It's important to keep in mind that these are the Supported Topologies involved in this scenario!</span></span> <span data-ttu-id="4deea-121">如果您需要移至支援封鎖方法的說明, 請參閱以下類型之間的配置。</span><span class="sxs-lookup"><span data-stu-id="4deea-121">If you need to go to Support for help with blocking a method, for example, you will need to have a configuration among the types below.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="4deea-122">在下面的表格和描述中,*新式驗證*為__MA__縮寫, 而*Windows 整合式驗證*則縮寫為__Win__。</span><span class="sxs-lookup"><span data-stu-id="4deea-122">In the table and descriptions below, *Modern Authentication* is abbreviated as __MA__ and *Windows Integrated Authentication* is abbreviated as __Win__.</span></span> <span data-ttu-id="4deea-123">在提醒中, Windows 整合式驗證是由兩種方法所組成: NTLM 和 Kerberos 驗證。</span><span class="sxs-lookup"><span data-stu-id="4deea-123">As a reminder, Windows Integrated Authentication is made up of two methods: NTLM and Kerberos authentication.</span></span> <span data-ttu-id="4deea-124">您必須知道此資訊才能正確閱讀表格!</span><span class="sxs-lookup"><span data-stu-id="4deea-124">You'll need to know this to read the table properly!</span></span>


|       |<span data-ttu-id="4deea-125">外部</span><span class="sxs-lookup"><span data-stu-id="4deea-125">Externally</span></span>  |<span data-ttu-id="4deea-126">內部</span><span class="sxs-lookup"><span data-stu-id="4deea-126">Internally</span></span>  |<span data-ttu-id="4deea-127">參數</span><span class="sxs-lookup"><span data-stu-id="4deea-127">Parameter</span></span>  |
|---------|:---------|:---------|---------|
|<span data-ttu-id="4deea-128">__輸入1__</span><span class="sxs-lookup"><span data-stu-id="4deea-128">__Type 1__</span></span>   |  <span data-ttu-id="4deea-129">MA + Win</span><span class="sxs-lookup"><span data-stu-id="4deea-129">MA + Win</span></span>       | <span data-ttu-id="4deea-130">MA + Win</span><span class="sxs-lookup"><span data-stu-id="4deea-130">MA + Win</span></span>         |  <span data-ttu-id="4deea-131">AllowAllExternallyAndInternally</span><span class="sxs-lookup"><span data-stu-id="4deea-131">AllowAllExternallyAndInternally</span></span>       |
|<span data-ttu-id="4deea-132">__輸入2__</span><span class="sxs-lookup"><span data-stu-id="4deea-132">__Type 2__</span></span>   |  <span data-ttu-id="4deea-133">購</span><span class="sxs-lookup"><span data-stu-id="4deea-133">MA</span></span>       | <span data-ttu-id="4deea-134">MA + Win</span><span class="sxs-lookup"><span data-stu-id="4deea-134">MA + Win</span></span>         | <span data-ttu-id="4deea-135">BlockWindowsAuthExternally</span><span class="sxs-lookup"><span data-stu-id="4deea-135">BlockWindowsAuthExternally</span></span>        |
|<span data-ttu-id="4deea-136">__鍵入3__</span><span class="sxs-lookup"><span data-stu-id="4deea-136">__Type 3__</span></span>   |  <span data-ttu-id="4deea-137">購</span><span class="sxs-lookup"><span data-stu-id="4deea-137">MA</span></span>       | <span data-ttu-id="4deea-138">購</span><span class="sxs-lookup"><span data-stu-id="4deea-138">MA</span></span>        | <span data-ttu-id="4deea-139">BlockWindowsAuthExternallyAndInternally</span><span class="sxs-lookup"><span data-stu-id="4deea-139">BlockWindowsAuthExternallyAndInternally</span></span>        |
|<span data-ttu-id="4deea-140">__輸入4__</span><span class="sxs-lookup"><span data-stu-id="4deea-140">__Type 4__</span></span>   |  <span data-ttu-id="4deea-141">購</span><span class="sxs-lookup"><span data-stu-id="4deea-141">MA</span></span>       | <span data-ttu-id="4deea-142">Win</span><span class="sxs-lookup"><span data-stu-id="4deea-142">Win</span></span>        | <span data-ttu-id="4deea-143">BlockWindowsAuthExternallyAndModernAuthInternally</span><span class="sxs-lookup"><span data-stu-id="4deea-143">BlockWindowsAuthExternallyAndModernAuthInternally</span></span>    |
|<span data-ttu-id="4deea-144">__輸入5__</span><span class="sxs-lookup"><span data-stu-id="4deea-144">__Type 5__</span></span>   |  <span data-ttu-id="4deea-145">MA + Win</span><span class="sxs-lookup"><span data-stu-id="4deea-145">MA + Win</span></span>       | <span data-ttu-id="4deea-146">Win</span><span class="sxs-lookup"><span data-stu-id="4deea-146">Win</span></span>        | <span data-ttu-id="4deea-147">BlockModernAuthInternally</span><span class="sxs-lookup"><span data-stu-id="4deea-147">BlockModernAuthInternally</span></span>         |

<span data-ttu-id="4deea-148">__鍵入1描述:__ 這是商務用 Skype Server 的 MA 開啟____ 時的預設情況。</span><span class="sxs-lookup"><span data-stu-id="4deea-148">__Type 1 Description:__ This is the default scenario when MA is turned __on__ for Skype for Business Server.</span></span> <span data-ttu-id="4deea-149">換句話說, 這是設定 MA 的*起點*。</span><span class="sxs-lookup"><span data-stu-id="4deea-149">In other words, this is the *starting point* when MA is configured.</span></span>

<span data-ttu-id="4deea-150">__輸入2描述:__ 此拓撲會在*外部*封鎖 ntlm, 但允許 Ntlm 或 Kerberos (適用于不支援 ADAL 的用戶端)*在內部*運作。</span><span class="sxs-lookup"><span data-stu-id="4deea-150">__Type 2 Description:__ This topology blocks NTLM *externally*, but allows NTLM or Kerberos (for clients that don't support ADAL) to work *internally*.</span></span> <span data-ttu-id="4deea-151">如果您的用戶端支援 ADAL, 它們將會在內部使用 MA。</span><span class="sxs-lookup"><span data-stu-id="4deea-151">If your clients  do support ADAL they will use MA internally.</span></span>

<span data-ttu-id="4deea-152">__鍵入3描述:__ 此拓朴需要 MA 才能讓所有使用者。</span><span class="sxs-lookup"><span data-stu-id="4deea-152">__Type 3 Description:__ This topology requires MA for all users.</span></span> <span data-ttu-id="4deea-153">您所有支援您的 ADAL 的用戶端都能在這個拓朴中運作, 例如, 如果您關閉使用密碼搭配憑證驗證, 就不會再利用密碼。</span><span class="sxs-lookup"><span data-stu-id="4deea-153">All your ADAL-capable clients will work in this topology, and passwords will not be leveraged if, for example, you turn off the use of passwords with Certificate-based Auth.</span></span>

<span data-ttu-id="4deea-154">__類型4說明:__ 此拓朴會在*外部*封鎖 NTLM, 並在內部封鎖 MA。</span><span class="sxs-lookup"><span data-stu-id="4deea-154">__Type 4 Description:__ This topology blocks NTLM *externally* and MA internally.</span></span> <span data-ttu-id="4deea-155">它可讓*所有用戶端\*\*在內部*使用舊版驗證方法 (即使是支援 ADAL 的用戶端)。</span><span class="sxs-lookup"><span data-stu-id="4deea-155">It allows *all clients* to use legacy authentication methods *internally* (even ADAL-capable clients).</span></span>

<span data-ttu-id="4deea-156">__輸入5描述:__*從外部*來看, 您現代的 ADAL 用戶端會使用 MA, 而任何不支援 ADAL 的用戶端都會使用舊版驗證方法。</span><span class="sxs-lookup"><span data-stu-id="4deea-156">__Type 5 Description:__ *Externally*, your modern ADAL clients will use MA and any clients that don't support ADAL will use legacy authentication methods.</span></span> <span data-ttu-id="4deea-157">但*在內部*,*所有用戶端*都會使用舊版驗證 (包括所有支援 ADAL 的用戶端)。</span><span class="sxs-lookup"><span data-stu-id="4deea-157">But, *internally* *all clients* will use legacy authentication (including all ADAL-capable clients).</span></span>

<span data-ttu-id="4deea-158">在可用選項中, 您很容易無法追蹤保護密碼的目標。</span><span class="sxs-lookup"><span data-stu-id="4deea-158">It's pretty easy to lose track of the goal of protecting your passwords in the options available.</span></span> <span data-ttu-id="4deea-159">請記住, 理想的情況是要在外部使用 MA (例如, 透過設定以證書為基礎的 auth) 來避免 DOS 攻擊。</span><span class="sxs-lookup"><span data-stu-id="4deea-159">Keep in mind the ideal situation is to use MA externally (for example, by configuring certificate-based auth), to avoid DOS attacks.</span></span> <span data-ttu-id="4deea-160">如果您是在內部針對現代用戶端利用它, 您也可以針對商務用 Skype Server DOS 攻擊, 進一步驗證您的網路。</span><span class="sxs-lookup"><span data-stu-id="4deea-160">If you leverage it internally for your modern clients, you'll also future-proof your network regarding Skype for Business Server DOS attacks.</span></span>

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a><span data-ttu-id="4deea-161">為什麼要在全域層級使用 Set CsAuthConfig</span><span class="sxs-lookup"><span data-stu-id="4deea-161">Why to use Set-CsAuthConfig at the Global level</span></span>

<span data-ttu-id="4deea-162">註冊`Set-CsAuthConfig`機和 Web 服務角色上的 Cmdlet 效果設定。</span><span class="sxs-lookup"><span data-stu-id="4deea-162">The `Set-CsAuthConfig` cmdlet effects configuration on both the Registrar and the Web Services roles.</span></span>

<span data-ttu-id="4deea-163">這個 Cmdlet 應該在您的商務用 Skype 伺服器的全域層級執行。</span><span class="sxs-lookup"><span data-stu-id="4deea-163">This cmdlet is meant to be run at the Global level of your Skype for Business server.</span></span> <span data-ttu-id="4deea-164">它*可以*在池層級執行, 但*不建議這樣做*, 因為這會增加安裝的複雜性。</span><span class="sxs-lookup"><span data-stu-id="4deea-164">It *can* be run at the Pool level but that is *not recommended* because it will add complexity to your installation.</span></span> <span data-ttu-id="4deea-165">在池層級執行這些命令時, 如果您的池沒有包含所有角色 (例如, 它沒有 Web 服務), 就只會針對註冊機構角色設定這些設定。</span><span class="sxs-lookup"><span data-stu-id="4deea-165">By running these commands at the Pool level, if your Pool doesn't have all of the roles included (for example, it doesn't have Web Services), the settings will only be set for the Registrar role.</span></span> <span data-ttu-id="4deea-166">在這種情況下, Web 服務將會使用來自全域層級的設定, 這可能會造成混亂的行為 (尤其是在無意中進行這項作業時)。</span><span class="sxs-lookup"><span data-stu-id="4deea-166">In that case, Web Services will carry on with settings from the Global level, which can be confusing behaviour (particularly when this is done unintentionally).</span></span>

<span data-ttu-id="4deea-167">如果用戶端使用來自某個池中的註冊機構設定, 以及來自另一個池的 Web 服務設定, 且驗證設定處於不一致的狀態, yous 用戶端可能無法登入。</span><span class="sxs-lookup"><span data-stu-id="4deea-167">If a client uses the Registrar settings from one pool and the Web Services settings from another pool and the authentication settings are in an inconsistent state, yous clients may be unable to log on.</span></span>

<span data-ttu-id="4deea-168">此外, 如果一個池只有一個角色存在:</span><span class="sxs-lookup"><span data-stu-id="4deea-168">Also, if there's only one role present for a pool:</span></span> 
* <span data-ttu-id="4deea-169">Set-只會設定對應至現有角色的設定。</span><span class="sxs-lookup"><span data-stu-id="4deea-169">Set- will only set the settings that correspond to the role that exists.</span></span> <span data-ttu-id="4deea-170">不會提供任何特殊的警告, 因為*尚未*設定部分設定。</span><span class="sxs-lookup"><span data-stu-id="4deea-170">No special warning will be given because some settings were *not* set.</span></span> 
* <span data-ttu-id="4deea-171">[取得]: 會傳回與現有角色對應的設定, 以及不存在角色的全域設定。</span><span class="sxs-lookup"><span data-stu-id="4deea-171">Get- will return the setting that corresponds to the role that exists, and the Global settings for the role that doesn't exist.</span></span>
* <span data-ttu-id="4deea-172">如果沒有任何角色存在於某個池, 則 [Set] 和 [取得] 都會傳回錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="4deea-172">If neither role is present for a pool, both Set- and Get- will return an error message.</span></span>
* <span data-ttu-id="4deea-173">如果有兩個角色都存在於某個池, 但原則沒有在池層級定義, 則 [取得] 會傳回錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="4deea-173">If both roles are present for a pool but policies aren't defined at the pool level, Get- will return an error message.</span></span>

<span data-ttu-id="4deea-174">您可以 wisest 來取得這些值, 以及在進行任何變更前, 從螢幕擷取畫面或記錄其起始狀態。</span><span class="sxs-lookup"><span data-stu-id="4deea-174">It may be wisest to do a Get- for these values, and to screenshot or record their starting state before making any changes.</span></span> <span data-ttu-id="4deea-175">您也可以考慮在 OneNote 中保留變更記錄。</span><span class="sxs-lookup"><span data-stu-id="4deea-175">You might also consider keeping a log of changes in a OneNote.</span></span>

> [!NOTE]
> 
> <span data-ttu-id="4deea-176">注意: 設定 CsAuthConfig 之後, 您必須在每台電腦上執行 Enable-CsComputer, 才能讓設定生效。</span><span class="sxs-lookup"><span data-stu-id="4deea-176">Note: After configuring the CsAuthConfig, you must run Enable-CsComputer on each computer in order for the settings to take effect.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4deea-177">如果您使用的是 Lync Web Access (LWA), 且必須使用以表單為基礎的 Access (FBA) 來進行外部存取, 請重新設定 LWA, 讓用戶端可以使用匿名存取來存取, 以支援這些案例。</span><span class="sxs-lookup"><span data-stu-id="4deea-177">If you're using Lync Web Access (LWA) and must use Forms-based Access (FBA) for external access, reconfigure LWA so that clients can access it with Anonymous Access to support these scenarios.</span></span> <span data-ttu-id="4deea-178">同樣地, 如果您使用撥入 Pin, 將只對外部使用者封鎖 FBA。</span><span class="sxs-lookup"><span data-stu-id="4deea-178">Likewise, if you use Dial-in Pin, FBA will be blocked for external users only.</span></span> <span data-ttu-id="4deea-179">如果他們需要變更其 pin, 必須在內部登入其公司以執行此動作。</span><span class="sxs-lookup"><span data-stu-id="4deea-179">If they need to change their pin, they will need to login to their corporation to do so, internally.</span></span>

## <a name="links"></a><span data-ttu-id="4deea-180">鏈路</span><span class="sxs-lookup"><span data-stu-id="4deea-180">Links</span></span> 
- <span data-ttu-id="4deea-181">如需更多 PowerShell 資訊:</span><span class="sxs-lookup"><span data-stu-id="4deea-181">For more PowerShell information:</span></span>
    -  [<span data-ttu-id="4deea-182">CsAuthConfig</span><span class="sxs-lookup"><span data-stu-id="4deea-182">Get-CsAuthConfig</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [<span data-ttu-id="4deea-183">Set-CsAuthConfig</span><span class="sxs-lookup"><span data-stu-id="4deea-183">Set-CsAuthConfig</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/set-csauthconfig?view=skype-ps)

- <span data-ttu-id="4deea-184">如需更多關於如何使用命令或安裝的指示, 請執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="4deea-184">For more direction on how to use the commands or on the CU needed to install them:</span></span>
    - [<span data-ttu-id="4deea-185">Cmdlet 簡介</span><span class="sxs-lookup"><span data-stu-id="4deea-185">Cmdlets briefing</span></span>](https://support.microsoft.com/en-us/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - <span data-ttu-id="4deea-186">[商務用 Skype Server 2015 的更新](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)一般</span><span class="sxs-lookup"><span data-stu-id="4deea-186">[Updates for Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015) (General)</span></span>
    - <span data-ttu-id="4deea-187">[2018 年7月商務用 Skype Server 2015, 核心元件 CU](https://support.microsoft.com/en-us/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)</span><span class="sxs-lookup"><span data-stu-id="4deea-187">The [July 2018 Skype for Business Server 2015, Core Components CU](https://support.microsoft.com/en-us/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)</span></span>


 
