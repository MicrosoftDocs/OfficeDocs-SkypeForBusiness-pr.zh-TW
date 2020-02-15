---
title: 若要關閉傳統驗證方法從內部和外部到您的網路規劃
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 此文章概述 cmdlet 可讓系統管理員更多控制的驗證方法使用，內外，商務版。 系統管理員可以開啟的驗證方法] 或 [關閉內部或外部他們的網路。
ms.openlocfilehash: a3f26e0bb29a58b53547083a4410da849c054b03
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043715"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a><span data-ttu-id="f5573-104">規劃關閉傳統驗證方法在內部及外部網路。</span><span class="sxs-lookup"><span data-stu-id="f5573-104">Planning to turn off Legacy authentication methods internally and externally to your network.</span></span>

> [!NOTE]
> <span data-ttu-id="f5573-105">如果您是要閱讀這篇文章，您應該已了解支援的新式驗證拓撲，ADAL，以及有關新式驗證設定，但，以防您不等待，以下是開始所需的文章：</span><span class="sxs-lookup"><span data-stu-id="f5573-105">If you're about to read this article, you should already know about supported Modern Authentication topologies, ADAL, and about Modern Authentication config, but, in case you don't, here are the articles you need to start out:</span></span> 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
<span data-ttu-id="f5573-106">新式驗證不只是啟用更安全的驗證，例如雙因素驗證或憑證型驗證的方法，它可以按照您使用者的授權不太需要使用者名稱或密碼。</span><span class="sxs-lookup"><span data-stu-id="f5573-106">Modern Authentication doesn't just enable more secure methods of authentication, like Two-Factor Auth, or Certificate-based Auth, it can carry out authorization of your user without needing a username or password too.</span></span> <span data-ttu-id="f5573-107">它就很方便。</span><span class="sxs-lookup"><span data-stu-id="f5573-107">It's pretty handy.</span></span>

<span data-ttu-id="f5573-108">本文可協助您有商務伺服器，藉由關閉舊方法用來進行驗證，以外部方式、 內部或以上兩者、 您的網路利用的 Skype 上的服務拒絕 (DOS) 攻擊的隨漏洞。</span><span class="sxs-lookup"><span data-stu-id="f5573-108">This article will help you plug holes that have been exploited for Denial Of Service (DOS) attacks on Skype for Business Servers, by turning off older methods used for authentication, externally, internally, or both, to your network.</span></span> <span data-ttu-id="f5573-109">例如，以協助停止 DOS 攻擊的一個好方法是關閉 Windows 整合式驗證 （其中包含 NTLM 和 Kerberos）。</span><span class="sxs-lookup"><span data-stu-id="f5573-109">For example, one good method to help stop DOS attacks would be to turn off Windows Integrated Authentication (which includes NTLM and Kerberos).</span></span> <span data-ttu-id="f5573-110">外部關閉 NTLM 和依賴憑證型驗證可以協助保護密碼從曝光度。</span><span class="sxs-lookup"><span data-stu-id="f5573-110">Turning off NTLM externally and relying on certificate-based authentication helps to protect passwords from exposure.</span></span> <span data-ttu-id="f5573-111">這是因為 NTLM 使用密碼認證來驗證使用者，但憑證型驗證-啟用新式驗證-不會。</span><span class="sxs-lookup"><span data-stu-id="f5573-111">This is because NTLM uses password credentials to authenticate users, but certificate-based authentication -- enabled by Modern Auth -- doesn't.</span></span> <span data-ttu-id="f5573-112">表示一個理想的選項以降低拒絕服務攻擊是封鎖外部 NTLM 和使用唯一憑證型的驗證，改為。</span><span class="sxs-lookup"><span data-stu-id="f5573-112">That means one ideal option to reduce DOS attacks is to block NTLM externally, and use only certificate-based authentication there, instead.</span></span>

<span data-ttu-id="f5573-113">所有向右，讓我們開始。</span><span class="sxs-lookup"><span data-stu-id="f5573-113">All right, let's get started.</span></span>

## <a name="what-would-you-be-changing"></a><span data-ttu-id="f5573-114">什麼您時，必須變更？</span><span class="sxs-lookup"><span data-stu-id="f5573-114">What would you be changing?</span></span> 

<span data-ttu-id="f5573-115">這些 cmdlet 適用於 SIP 和 Web 服務的存取點。</span><span class="sxs-lookup"><span data-stu-id="f5573-115">These cmdlets work for both SIP and Web Services points of access.</span></span> <span data-ttu-id="f5573-116">雖然這些兩個通道使用不同的存取方法，從 NTLM 和 Kerberos 執行色階匿名存取，所有商務用 Skype 所使用的標準方法有已納入考量。</span><span class="sxs-lookup"><span data-stu-id="f5573-116">Though these two channels use different access methods, running the gamut from NTLM and Kerberos to Anonymous access, all standard methods used by Skype for Business have been taken into consideration.</span></span>

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a><span data-ttu-id="f5573-117">如何取得的取得和設定 CsAuthConfig cmdlet</span><span class="sxs-lookup"><span data-stu-id="f5573-117">How to get the Get- and Set-CsAuthConfig cmdlets</span></span>

<span data-ttu-id="f5573-118">這些指令程式將只會安裝張貼 2018 年 7 月累積更新 (6.0.9319.534) Microsoft skype Server 2015，，然後中的各種拓撲中，可以針對您 Skype for Business server 導入。</span><span class="sxs-lookup"><span data-stu-id="f5573-118">These cmdlets will only be installed post July 2018 cumulative update (6.0.9319.534) for Microsoft Skype for Business Server 2015, and then you have a variety of topologies that can be rolled out for your Skype for Business server.</span></span>

## <a name="topologies"></a><span data-ttu-id="f5573-119">拓撲</span><span class="sxs-lookup"><span data-stu-id="f5573-119">Topologies</span></span>

<span data-ttu-id="f5573-120">請務必記住，這些是支援的拓撲，在此案例中所涉及 ！</span><span class="sxs-lookup"><span data-stu-id="f5573-120">It's important to keep in mind that these are the Supported Topologies involved in this scenario!</span></span> <span data-ttu-id="f5573-121">如果您需要支援尋求協助以封鎖方法，例如，您必須有下列類型的設定。</span><span class="sxs-lookup"><span data-stu-id="f5573-121">If you need to go to Support for help with blocking a method, for example, you will need to have a configuration among the types below.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="f5573-122">在資料表和以下的說明，*新式驗證*縮寫成__MA__及*Windows 整合式驗證*縮寫成__Win__。</span><span class="sxs-lookup"><span data-stu-id="f5573-122">In the table and descriptions below, *Modern Authentication* is abbreviated as __MA__ and *Windows Integrated Authentication* is abbreviated as __Win__.</span></span> <span data-ttu-id="f5573-123">做為提醒，Windows 整合式驗證組成兩種方法： NTLM 和 Kerberos 驗證。</span><span class="sxs-lookup"><span data-stu-id="f5573-123">As a reminder, Windows Integrated Authentication is made up of two methods: NTLM and Kerberos authentication.</span></span> <span data-ttu-id="f5573-124">您必須知道此功能才能正確地讀取資料表 ！</span><span class="sxs-lookup"><span data-stu-id="f5573-124">You'll need to know this to read the table properly!</span></span>


|       |<span data-ttu-id="f5573-125">以外部方式</span><span class="sxs-lookup"><span data-stu-id="f5573-125">Externally</span></span>  |<span data-ttu-id="f5573-126">在內部</span><span class="sxs-lookup"><span data-stu-id="f5573-126">Internally</span></span>  |<span data-ttu-id="f5573-127">參數</span><span class="sxs-lookup"><span data-stu-id="f5573-127">Parameter</span></span>  |
|---------|:---------|:---------|---------|
|<span data-ttu-id="f5573-128">__類型 1__</span><span class="sxs-lookup"><span data-stu-id="f5573-128">__Type 1__</span></span>   |  <span data-ttu-id="f5573-129">MA + Win</span><span class="sxs-lookup"><span data-stu-id="f5573-129">MA + Win</span></span>       | <span data-ttu-id="f5573-130">MA + Win</span><span class="sxs-lookup"><span data-stu-id="f5573-130">MA + Win</span></span>         |  <span data-ttu-id="f5573-131">AllowAllExternallyAndInternally</span><span class="sxs-lookup"><span data-stu-id="f5573-131">AllowAllExternallyAndInternally</span></span>       |
|<span data-ttu-id="f5573-132">__類型 2__</span><span class="sxs-lookup"><span data-stu-id="f5573-132">__Type 2__</span></span>   |  <span data-ttu-id="f5573-133">MA</span><span class="sxs-lookup"><span data-stu-id="f5573-133">MA</span></span>       | <span data-ttu-id="f5573-134">MA + Win</span><span class="sxs-lookup"><span data-stu-id="f5573-134">MA + Win</span></span>         | <span data-ttu-id="f5573-135">BlockWindowsAuthExternally</span><span class="sxs-lookup"><span data-stu-id="f5573-135">BlockWindowsAuthExternally</span></span>        |
|<span data-ttu-id="f5573-136">__類型 3__</span><span class="sxs-lookup"><span data-stu-id="f5573-136">__Type 3__</span></span>   |  <span data-ttu-id="f5573-137">MA</span><span class="sxs-lookup"><span data-stu-id="f5573-137">MA</span></span>       | <span data-ttu-id="f5573-138">MA</span><span class="sxs-lookup"><span data-stu-id="f5573-138">MA</span></span>        | <span data-ttu-id="f5573-139">BlockWindowsAuthExternallyAndInternally</span><span class="sxs-lookup"><span data-stu-id="f5573-139">BlockWindowsAuthExternallyAndInternally</span></span>        |
|<span data-ttu-id="f5573-140">__類型 4__</span><span class="sxs-lookup"><span data-stu-id="f5573-140">__Type 4__</span></span>   |  <span data-ttu-id="f5573-141">MA</span><span class="sxs-lookup"><span data-stu-id="f5573-141">MA</span></span>       | <span data-ttu-id="f5573-142">Win</span><span class="sxs-lookup"><span data-stu-id="f5573-142">Win</span></span>        | <span data-ttu-id="f5573-143">BlockWindowsAuthExternallyAndModernAuthInternally</span><span class="sxs-lookup"><span data-stu-id="f5573-143">BlockWindowsAuthExternallyAndModernAuthInternally</span></span>    |
|<span data-ttu-id="f5573-144">__類型 5__</span><span class="sxs-lookup"><span data-stu-id="f5573-144">__Type 5__</span></span>   |  <span data-ttu-id="f5573-145">MA + Win</span><span class="sxs-lookup"><span data-stu-id="f5573-145">MA + Win</span></span>       | <span data-ttu-id="f5573-146">Win</span><span class="sxs-lookup"><span data-stu-id="f5573-146">Win</span></span>        | <span data-ttu-id="f5573-147">BlockModernAuthInternally</span><span class="sxs-lookup"><span data-stu-id="f5573-147">BlockModernAuthInternally</span></span>         |

<span data-ttu-id="f5573-148">__中，輸入 1 的描述：__ 這是預設__案例 MA 時開啟 skype for Business Server__ 。</span><span class="sxs-lookup"><span data-stu-id="f5573-148">__Type 1 Description:__ This is the default scenario when MA is turned __on__ for Skype for Business Server.</span></span> <span data-ttu-id="f5573-149">換句話說，這是*起始點*的 MA 設定時。</span><span class="sxs-lookup"><span data-stu-id="f5573-149">In other words, this is the *starting point* when MA is configured.</span></span>

<span data-ttu-id="f5573-150">__類型 2 描述：__ 這種拓撲封鎖 NTLM*外部*，但可容許 NTLM 或 Kerberos （用戶端不支援 ADAL） 若要*在內部*使用。</span><span class="sxs-lookup"><span data-stu-id="f5573-150">__Type 2 Description:__ This topology blocks NTLM *externally*, but allows NTLM or Kerberos (for clients that don't support ADAL) to work *internally*.</span></span> <span data-ttu-id="f5573-151">如果您的用戶端支援 ADAL 他們會在內部使用 MA。</span><span class="sxs-lookup"><span data-stu-id="f5573-151">If your clients  do support ADAL they will use MA internally.</span></span>

<span data-ttu-id="f5573-152">__類型 3 描述：__ 此拓撲需要 MA 的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="f5573-152">__Type 3 Description:__ This topology requires MA for all users.</span></span> <span data-ttu-id="f5573-153">所有 ADAL 具備用戶端會在此拓撲中，都運作，而且如果您關閉使用憑證型驗證]。 使用的密碼，例如，不利用密碼</span><span class="sxs-lookup"><span data-stu-id="f5573-153">All your ADAL-capable clients will work in this topology, and passwords will not be leveraged if, for example, you turn off the use of passwords with Certificate-based Auth.</span></span>

<span data-ttu-id="f5573-154">__類型 4 描述：__ 這種拓撲內部封鎖 NTLM*外部*和 MA。</span><span class="sxs-lookup"><span data-stu-id="f5573-154">__Type 4 Description:__ This topology blocks NTLM *externally* and MA internally.</span></span> <span data-ttu-id="f5573-155">它可讓*所有的用戶端*使用舊版的驗證方法*在內部*（甚至 ADAL 具備用戶端）。</span><span class="sxs-lookup"><span data-stu-id="f5573-155">It allows *all clients* to use legacy authentication methods *internally* (even ADAL-capable clients).</span></span>

<span data-ttu-id="f5573-156">__類型 5 描述：__ *外部*新式 ADAL 用戶端會使用 MA 及不支援 ADAL 任何用戶端將使用傳統驗證方法。</span><span class="sxs-lookup"><span data-stu-id="f5573-156">__Type 5 Description:__ *Externally*, your modern ADAL clients will use MA and any clients that don't support ADAL will use legacy authentication methods.</span></span> <span data-ttu-id="f5573-157">但是，*在內部\*\*所有用戶端*將使用傳統驗證 （包括所有的 ADAL 具備用戶端）。</span><span class="sxs-lookup"><span data-stu-id="f5573-157">But, *internally* *all clients* will use legacy authentication (including all ADAL-capable clients).</span></span>

<span data-ttu-id="f5573-158">它是目標的很容易就能遺失保護您的密碼中可用的選項的追蹤記錄。</span><span class="sxs-lookup"><span data-stu-id="f5573-158">It's pretty easy to lose track of the goal of protecting your passwords in the options available.</span></span> <span data-ttu-id="f5573-159">請記得理想的情況下是使用外部 MA （例如，藉由設定憑證型驗證），以避免 DOS 攻擊。</span><span class="sxs-lookup"><span data-stu-id="f5573-159">Keep in mind the ideal situation is to use MA externally (for example, by configuring certificate-based auth), to avoid DOS attacks.</span></span> <span data-ttu-id="f5573-160">如果您利用其內部新式的用戶端，您將也未來證明 Business Server DOS 攻擊的 Skype 有關網路。</span><span class="sxs-lookup"><span data-stu-id="f5573-160">If you leverage it internally for your modern clients, you'll also future-proof your network regarding Skype for Business Server DOS attacks.</span></span>

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a><span data-ttu-id="f5573-161">若要使用集 CsAuthConfig 全域層級的原因</span><span class="sxs-lookup"><span data-stu-id="f5573-161">Why to use Set-CsAuthConfig at the Global level</span></span>

<span data-ttu-id="f5573-162">`Set-CsAuthConfig`登錄器和 Web 服務角色上的指令程式效果設定。</span><span class="sxs-lookup"><span data-stu-id="f5573-162">The `Set-CsAuthConfig` cmdlet effects configuration on both the Registrar and the Web Services roles.</span></span>

<span data-ttu-id="f5573-163">此 cmdlet 是用來執行您 Skype for Business server 全域層級。</span><span class="sxs-lookup"><span data-stu-id="f5573-163">This cmdlet is meant to be run at the Global level of your Skype for Business server.</span></span> <span data-ttu-id="f5573-164">它*可以*在集區層級，但也就是*不建議您*執行，因為它會將複雜性新增至您的安裝。</span><span class="sxs-lookup"><span data-stu-id="f5573-164">It *can* be run at the Pool level but that is *not recommended* because it will add complexity to your installation.</span></span> <span data-ttu-id="f5573-165">在集區層級，執行下列命令，如果您的集區都不會有的所有角色包含 （例如，它不會有 Web 服務），設定才會設定登錄器角色。</span><span class="sxs-lookup"><span data-stu-id="f5573-165">By running these commands at the Pool level, if your Pool doesn't have all of the roles included (for example, it doesn't have Web Services), the settings will only be set for the Registrar role.</span></span> <span data-ttu-id="f5573-166">在此情況下，Web 服務會繼續進行全域層級，可能會令人費解的行為 （尤其是當這是不小心） 設定。</span><span class="sxs-lookup"><span data-stu-id="f5573-166">In that case, Web Services will carry on with settings from the Global level, which can be confusing behaviour (particularly when this is done unintentionally).</span></span>

<span data-ttu-id="f5573-167">如果用戶端使用的登錄器設定從一個集區及 Web 服務設定從另一個集區和驗證設定是以一致的狀態，yous 用戶端可能無法登入。</span><span class="sxs-lookup"><span data-stu-id="f5573-167">If a client uses the Registrar settings from one pool and the Web Services settings from another pool and the authentication settings are in an inconsistent state, yous clients may be unable to log on.</span></span>

<span data-ttu-id="f5573-168">此外，如果沒有只能有一個角色存在的集區：</span><span class="sxs-lookup"><span data-stu-id="f5573-168">Also, if there's only one role present for a pool:</span></span> 
* <span data-ttu-id="f5573-169">設定將只會設定為存在的角色的對應的設定。</span><span class="sxs-lookup"><span data-stu-id="f5573-169">Set- will only set the settings that correspond to the role that exists.</span></span> <span data-ttu-id="f5573-170">會不指定任何特殊的警告，因為某些設定*不*設定。</span><span class="sxs-lookup"><span data-stu-id="f5573-170">No special warning will be given because some settings were *not* set.</span></span> 
* <span data-ttu-id="f5573-171">取得會傳回對應至已存在，角色的設定及不存在的角色的全域設定。</span><span class="sxs-lookup"><span data-stu-id="f5573-171">Get- will return the setting that corresponds to the role that exists, and the Global settings for the role that doesn't exist.</span></span>
* <span data-ttu-id="f5573-172">如果不角色已存在的集區，這兩個 Set 與 Get 會傳回一則錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="f5573-172">If neither role is present for a pool, both Set- and Get- will return an error message.</span></span>
* <span data-ttu-id="f5573-173">如果兩個角色都存在的集區，但未定義在集區層級的原則，取得將會傳回一則錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="f5573-173">If both roles are present for a pool but policies aren't defined at the pool level, Get- will return an error message.</span></span>

<span data-ttu-id="f5573-174">它可能整理到執行 Get-，這些值，與螢幕擷取畫面或進行任何變更之前錄製其起始狀態。</span><span class="sxs-lookup"><span data-stu-id="f5573-174">It may be wisest to do a Get- for these values, and to screenshot or record their starting state before making any changes.</span></span> <span data-ttu-id="f5573-175">您也可以考慮在 OneNote 中保留變更記錄檔。</span><span class="sxs-lookup"><span data-stu-id="f5573-175">You might also consider keeping a log of changes in a OneNote.</span></span>

> [!NOTE]
> 
> <span data-ttu-id="f5573-176">附註： 設定 CsAuthConfig 之後, 您必須執行 Enable-cscomputer，設定才會生效的順序中的每部電腦上。</span><span class="sxs-lookup"><span data-stu-id="f5573-176">Note: After configuring the CsAuthConfig, you must run Enable-CsComputer on each computer in order for the settings to take effect.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5573-177">如果您使用 Lync Web Access (LWA)，而且必須將表單為基礎的存取 (FBA) 用於外部存取，請重新設定 LWA，讓用戶端可以存取它利用匿名存取以支援這些案例。</span><span class="sxs-lookup"><span data-stu-id="f5573-177">If you're using Lync Web Access (LWA) and must use Forms-based Access (FBA) for external access, reconfigure LWA so that clients can access it with Anonymous Access to support these scenarios.</span></span> <span data-ttu-id="f5573-178">同樣地，如果您使用撥入 Pin，FBA 也將遭到封鎖外部的使用者。</span><span class="sxs-lookup"><span data-stu-id="f5573-178">Likewise, if you use Dial-in Pin, FBA will be blocked for external users only.</span></span> <span data-ttu-id="f5573-179">如果他們需要變更他們的 pin 碼，他們必須登入至其公司若要這麼做，請在內部。</span><span class="sxs-lookup"><span data-stu-id="f5573-179">If they need to change their pin, they will need to login to their corporation to do so, internally.</span></span>

> [!NOTE]
> 
> <span data-ttu-id="f5573-180">如果您要從外部封鎖 NTLM 使用 BlockWindowsAuthExternally 參數，請注意這也會封鎖 NTLM 內部 SIP 通道。</span><span class="sxs-lookup"><span data-stu-id="f5573-180">If you use the BlockWindowsAuthExternally parameter to externally block NTLM, be aware this also blocks NTLM internally for the SIP channel.</span></span> <span data-ttu-id="f5573-181">不過，Skype for Business 和 Lync 用戶端，較新比 2010年仍無法登入，因為它們會使用 NTLM over HTTP 的登入，就內部而言，over SIP 然後擷取登入的憑證。</span><span class="sxs-lookup"><span data-stu-id="f5573-181">However, Skype for Business and Lync clients newer than 2010 will still be able to login because they will use NTLM over HTTP for signin, internally, and then fetch a certificate to login over SIP.</span></span> <span data-ttu-id="f5573-182">不過，超過 2010年用戶端將無法登入內部這種情況下，以及您可能要考慮這些應用程式升級，讓您的使用者可以繼續安全的功能。</span><span class="sxs-lookup"><span data-stu-id="f5573-182">However, clients older than 2010 will not be able to login internally in this circumstance, and you may want to consider upgrading these applications so that your users can resume secure functionality.</span></span>


## <a name="links"></a><span data-ttu-id="f5573-183">Links</span><span class="sxs-lookup"><span data-stu-id="f5573-183">Links</span></span> 
- <span data-ttu-id="f5573-184">如需 PowerShell 資訊：</span><span class="sxs-lookup"><span data-stu-id="f5573-184">For more PowerShell information:</span></span>
    -  [<span data-ttu-id="f5573-185">取得 CsAuthConfig</span><span class="sxs-lookup"><span data-stu-id="f5573-185">Get-CsAuthConfig</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [<span data-ttu-id="f5573-186">設定 CsAuthConfig</span><span class="sxs-lookup"><span data-stu-id="f5573-186">Set-CsAuthConfig</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csauthconfig?view=skype-ps)

- <span data-ttu-id="f5573-187">如何使用命令或上安裝這些所需的 CU 的多個方向：</span><span class="sxs-lookup"><span data-stu-id="f5573-187">For more direction on how to use the commands or on the CU needed to install them:</span></span>
    - [<span data-ttu-id="f5573-188">Cmdlet 簡報</span><span class="sxs-lookup"><span data-stu-id="f5573-188">Cmdlets briefing</span></span>](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - <span data-ttu-id="f5573-189">[Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) （一般）</span><span class="sxs-lookup"><span data-stu-id="f5573-189">[Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) (General)</span></span>
    - <span data-ttu-id="f5573-190">[2018 年 7 月 Skype for Business Server 2015，核心元件 CU](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)</span><span class="sxs-lookup"><span data-stu-id="f5573-190">The [July 2018 Skype for Business Server 2015, Core Components CU](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)</span></span>


 
