---
title: 規劃在內部和外部將舊版驗證方法關閉至您的網路
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
description: 本文概述可讓系統管理員進一步控制企業內部和外部使用之驗證方法的 Cmdlet。 系統管理員可以在內部或外部開啟或關閉驗證方法，或從外部關閉驗證方法。
ms.openlocfilehash: 21aacd6514ee9e47087906292564eea7aede7ead
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815811"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>規劃在內部和外部將舊版驗證方法關閉至您的網路。

> [!NOTE]
> 如果您要閱讀本文，您應該已經知道支援的新式驗證拓撲、ADAL，以及關於新式驗證配置，但如果您不這麼做，以下是您需要開始的文章： 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
新式驗證並不只是啟用更安全的驗證方法（例如雙因素驗證，或以證書為基礎的驗證），只要不需要使用者名稱或密碼，就能自行執行您的使用者授權。 這相當簡單。

本文將協助您插入在商務用 Skype 伺服器上受到拒絕服務（DOS）攻擊的漏洞，方法是關閉針對您的網路進行驗證所使用的較舊的方法。 例如，協助停止 DOS 攻擊的一個好方法就是關閉 Windows 整合驗證（包括 NTLM 與 Kerberos）。 在外部關閉 NTLM 並依賴憑證式驗證可協助保護密碼免遭洩密。 這是因為 NTLM 使用密碼認證來驗證使用者，但認證驗證（由新式驗證所啟用）不是。 這表示減少 DOS 攻擊的一個理想選擇就是封鎖外部的 NTLM，並改為在這裡使用憑證式驗證。

完全正確，讓我們開始吧。

## <a name="what-would-you-be-changing"></a>您要變更什麼？ 

這些 Cmdlet 適用于 SIP 和 Web 服務存取點。 雖然這兩個通道使用不同的存取方法，請執行從 NTLM 與 Kerberos 到匿名存取的 gamut，否則已考慮商務用 Skype 所使用的所有標準方法。

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>如何取得 CsAuthConfig 和設定的 Cmdlet

這些 Cmdlet 只會安裝在 Microsoft 商務用 Skype Server 2015 的2018年7月的累加更新（6.0.9319.534）之後，您就可以針對您的商務用 Skype 伺服器推出多種不同的拓撲。

## <a name="topologies"></a>形

請務必記住，這種情況下會涉及以下所支援的拓撲！ 如果您需要移至支援封鎖方法的說明，請參閱以下類型之間的配置。 

> [!IMPORTANT]
> 在下面的表格和描述中，*新式驗證*為__MA__縮寫，而*Windows 整合式驗證*則縮寫為__Win__。 在提醒中，Windows 整合式驗證是由兩種方法所組成： NTLM 和 Kerberos 驗證。 您必須知道此資訊才能正確閱讀表格！


|       |外部  |內部  |參數  |
|---------|:---------|:---------|---------|
|__輸入1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__輸入2__   |  購       | MA + Win         | BlockWindowsAuthExternally        |
|__鍵入3__   |  購       | 購        | BlockWindowsAuthExternallyAndInternally        |
|__輸入4__   |  購       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__輸入5__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__鍵入1描述：__ 這是商務用 Skype __Server 的 MA 開啟時__的預設情況。 換句話說，這是設定 MA 的*起點*。

__輸入2描述：__ 此拓撲會在*外部*封鎖 ntlm，但允許 Ntlm 或 Kerberos （適用于不支援 ADAL 的用戶端）*在內部*運作。 如果您的用戶端支援 ADAL，它們將會在內部使用 MA。

__鍵入3描述：__ 此拓朴需要 MA 才能讓所有使用者。 您所有支援您的 ADAL 的用戶端都能在這個拓朴中運作，例如，如果您關閉使用密碼搭配憑證驗證，就不會再利用密碼。

__類型4說明：__ 此拓朴會在*外部*封鎖 NTLM，並在內部封鎖 MA。 它可讓*所有用戶端**在內部*使用舊版驗證方法（即使是支援 ADAL 的用戶端）。

__輸入5說明：__ *外部*，您的新式 ADAL 用戶端將使用 MA，而任何不支援 ADAL 的用戶端都會使用舊版驗證方法。 但*在內部*，*所有用戶端*都會使用舊版驗證（包括所有支援 ADAL 的用戶端）。

在可用選項中，您很容易無法追蹤保護密碼的目標。 請記住，理想的情況是要在外部使用 MA （例如，透過設定以證書為基礎的 auth）來避免 DOS 攻擊。 如果您是在內部針對現代用戶端利用它，您也可以針對商務用 Skype Server DOS 攻擊，進一步驗證您的網路。

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>為什麼要在全域層級使用 Set CsAuthConfig

註冊`Set-CsAuthConfig`機和 Web 服務角色上的 Cmdlet 效果設定。

這個 Cmdlet 應該在您的商務用 Skype 伺服器的全域層級執行。 它*可以*在池層級執行，但*不建議這樣做*，因為這會增加安裝的複雜性。 在池層級執行這些命令時，如果您的池沒有包含所有角色（例如，它沒有 Web 服務），就只會針對註冊機構角色設定這些設定。 在這種情況下，Web 服務將會使用來自全域層級的設定，這可能會造成混亂的行為（尤其是在無意中進行這項作業時）。

如果用戶端使用來自某個池中的註冊機構設定，以及來自另一個池的 Web 服務設定，且驗證設定處於不一致的狀態，yous 用戶端可能無法登入。

此外，如果一個池只有一個角色存在： 
* Set-只會設定對應至現有角色的設定。 不會提供任何特殊的警告，因為*尚未*設定部分設定。 
* [取得]：會傳回與現有角色對應的設定，以及不存在角色的全域設定。
* 如果沒有任何角色存在於某個池，則 [Set] 和 [取得] 都會傳回錯誤訊息。
* 如果有兩個角色都存在於某個池，但原則沒有在池層級定義，則 [取得] 會傳回錯誤訊息。

您可以 wisest 來取得這些值，以及在進行任何變更前，從螢幕擷取畫面或記錄其起始狀態。 您也可以考慮在 OneNote 中保留變更記錄。

> [!NOTE]
> 
> 注意：設定 CsAuthConfig 之後，您必須在每台電腦上執行 Enable-CsComputer，才能讓設定生效。

> [!IMPORTANT]
> 如果您使用的是 Lync Web Access （LWA），且必須使用以表單為基礎的 Access （FBA）來進行外部存取，請重新設定 LWA，讓用戶端可以使用匿名存取來存取，以支援這些案例。 同樣地，如果您使用撥入 Pin，將只對外部使用者封鎖 FBA。 如果他們需要變更其 pin，必須在內部登入其公司以執行此動作。

> [!NOTE]
> 
> 如果您使用 BlockWindowsAuthExternally 參數來外部封鎖 NTLM，請注意，這也會在內部封鎖 SIP 通道的 NTLM。 不過，比2010更新的商務用 Skype 和 Lync 用戶端仍能登入，因為他們將在內部使用 NTLM 透過 HTTP 登入，然後取得憑證來透過 SIP 登入。 不過，在這種情況下，超過2010的用戶端將無法在內部登入，而且您可能會想要考慮升級這些應用程式，讓您的使用者能夠繼續安全的功能。


## <a name="links"></a>鏈路 
- 如需更多 PowerShell 資訊：
    -  [CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/set-csauthconfig?view=skype-ps)

- 如需更多關於如何使用命令或安裝的指示，請執行下列動作：
    - [Cmdlet 簡介](https://support.microsoft.com/en-us/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [商務用 Skype Server 2015 的更新](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)（一般）
    - [2018 年7月商務用 Skype Server 2015，核心元件 CU](https://support.microsoft.com/en-us/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) （6.0.9319.534）


 
