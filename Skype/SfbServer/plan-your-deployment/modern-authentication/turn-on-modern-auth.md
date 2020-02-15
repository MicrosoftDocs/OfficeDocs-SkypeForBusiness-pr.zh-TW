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
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>規劃關閉傳統驗證方法在內部及外部網路。

> [!NOTE]
> 如果您是要閱讀這篇文章，您應該已了解支援的新式驗證拓撲，ADAL，以及有關新式驗證設定，但，以防您不等待，以下是開始所需的文章： 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
新式驗證不只是啟用更安全的驗證，例如雙因素驗證或憑證型驗證的方法，它可以按照您使用者的授權不太需要使用者名稱或密碼。 它就很方便。

本文可協助您有商務伺服器，藉由關閉舊方法用來進行驗證，以外部方式、 內部或以上兩者、 您的網路利用的 Skype 上的服務拒絕 (DOS) 攻擊的隨漏洞。 例如，以協助停止 DOS 攻擊的一個好方法是關閉 Windows 整合式驗證 （其中包含 NTLM 和 Kerberos）。 外部關閉 NTLM 和依賴憑證型驗證可以協助保護密碼從曝光度。 這是因為 NTLM 使用密碼認證來驗證使用者，但憑證型驗證-啟用新式驗證-不會。 表示一個理想的選項以降低拒絕服務攻擊是封鎖外部 NTLM 和使用唯一憑證型的驗證，改為。

所有向右，讓我們開始。

## <a name="what-would-you-be-changing"></a>什麼您時，必須變更？ 

這些 cmdlet 適用於 SIP 和 Web 服務的存取點。 雖然這些兩個通道使用不同的存取方法，從 NTLM 和 Kerberos 執行色階匿名存取，所有商務用 Skype 所使用的標準方法有已納入考量。

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>如何取得的取得和設定 CsAuthConfig cmdlet

這些指令程式將只會安裝張貼 2018 年 7 月累積更新 (6.0.9319.534) Microsoft skype Server 2015，，然後中的各種拓撲中，可以針對您 Skype for Business server 導入。

## <a name="topologies"></a>拓撲

請務必記住，這些是支援的拓撲，在此案例中所涉及 ！ 如果您需要支援尋求協助以封鎖方法，例如，您必須有下列類型的設定。 

> [!IMPORTANT]
> 在資料表和以下的說明，*新式驗證*縮寫成__MA__及*Windows 整合式驗證*縮寫成__Win__。 做為提醒，Windows 整合式驗證組成兩種方法： NTLM 和 Kerberos 驗證。 您必須知道此功能才能正確地讀取資料表 ！


|       |以外部方式  |在內部  |參數  |
|---------|:---------|:---------|---------|
|__類型 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__類型 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__類型 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__類型 4__   |  MA       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__類型 5__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__中，輸入 1 的描述：__ 這是預設__案例 MA 時開啟 skype for Business Server__ 。 換句話說，這是*起始點*的 MA 設定時。

__類型 2 描述：__ 這種拓撲封鎖 NTLM*外部*，但可容許 NTLM 或 Kerberos （用戶端不支援 ADAL） 若要*在內部*使用。 如果您的用戶端支援 ADAL 他們會在內部使用 MA。

__類型 3 描述：__ 此拓撲需要 MA 的所有使用者。 所有 ADAL 具備用戶端會在此拓撲中，都運作，而且如果您關閉使用憑證型驗證]。 使用的密碼，例如，不利用密碼

__類型 4 描述：__ 這種拓撲內部封鎖 NTLM*外部*和 MA。 它可讓*所有的用戶端*使用舊版的驗證方法*在內部*（甚至 ADAL 具備用戶端）。

__類型 5 描述：__ *外部*新式 ADAL 用戶端會使用 MA 及不支援 ADAL 任何用戶端將使用傳統驗證方法。 但是，*在內部**所有用戶端*將使用傳統驗證 （包括所有的 ADAL 具備用戶端）。

它是目標的很容易就能遺失保護您的密碼中可用的選項的追蹤記錄。 請記得理想的情況下是使用外部 MA （例如，藉由設定憑證型驗證），以避免 DOS 攻擊。 如果您利用其內部新式的用戶端，您將也未來證明 Business Server DOS 攻擊的 Skype 有關網路。

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>若要使用集 CsAuthConfig 全域層級的原因

`Set-CsAuthConfig`登錄器和 Web 服務角色上的指令程式效果設定。

此 cmdlet 是用來執行您 Skype for Business server 全域層級。 它*可以*在集區層級，但也就是*不建議您*執行，因為它會將複雜性新增至您的安裝。 在集區層級，執行下列命令，如果您的集區都不會有的所有角色包含 （例如，它不會有 Web 服務），設定才會設定登錄器角色。 在此情況下，Web 服務會繼續進行全域層級，可能會令人費解的行為 （尤其是當這是不小心） 設定。

如果用戶端使用的登錄器設定從一個集區及 Web 服務設定從另一個集區和驗證設定是以一致的狀態，yous 用戶端可能無法登入。

此外，如果沒有只能有一個角色存在的集區： 
* 設定將只會設定為存在的角色的對應的設定。 會不指定任何特殊的警告，因為某些設定*不*設定。 
* 取得會傳回對應至已存在，角色的設定及不存在的角色的全域設定。
* 如果不角色已存在的集區，這兩個 Set 與 Get 會傳回一則錯誤訊息。
* 如果兩個角色都存在的集區，但未定義在集區層級的原則，取得將會傳回一則錯誤訊息。

它可能整理到執行 Get-，這些值，與螢幕擷取畫面或進行任何變更之前錄製其起始狀態。 您也可以考慮在 OneNote 中保留變更記錄檔。

> [!NOTE]
> 
> 附註： 設定 CsAuthConfig 之後, 您必須執行 Enable-cscomputer，設定才會生效的順序中的每部電腦上。

> [!IMPORTANT]
> 如果您使用 Lync Web Access (LWA)，而且必須將表單為基礎的存取 (FBA) 用於外部存取，請重新設定 LWA，讓用戶端可以存取它利用匿名存取以支援這些案例。 同樣地，如果您使用撥入 Pin，FBA 也將遭到封鎖外部的使用者。 如果他們需要變更他們的 pin 碼，他們必須登入至其公司若要這麼做，請在內部。

> [!NOTE]
> 
> 如果您要從外部封鎖 NTLM 使用 BlockWindowsAuthExternally 參數，請注意這也會封鎖 NTLM 內部 SIP 通道。 不過，Skype for Business 和 Lync 用戶端，較新比 2010年仍無法登入，因為它們會使用 NTLM over HTTP 的登入，就內部而言，over SIP 然後擷取登入的憑證。 不過，超過 2010年用戶端將無法登入內部這種情況下，以及您可能要考慮這些應用程式升級，讓您的使用者可以繼續安全的功能。


## <a name="links"></a>Links 
- 如需 PowerShell 資訊：
    -  [取得 CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [設定 CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/set-csauthconfig?view=skype-ps)

- 如何使用命令或上安裝這些所需的 CU 的多個方向：
    - [Cmdlet 簡報](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) （一般）
    - [2018 年 7 月 Skype for Business Server 2015，核心元件 CU](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


 
