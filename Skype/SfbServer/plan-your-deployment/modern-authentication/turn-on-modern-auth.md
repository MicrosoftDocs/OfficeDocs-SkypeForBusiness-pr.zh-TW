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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: 本文概述的 Cmdlet 可讓系統管理員更深入地控制企業內部及外部使用的驗證方法。 管理員可以在內部或外部開啟或關閉驗證方法。
ms.openlocfilehash: 7bad18e79e1595c7dfe4518d73b6dd764e313e22
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601358"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>規劃在內部和外部關閉舊版驗證方法。

> [!NOTE]
> 如果您即將閱讀本文，您應該已經知道支援的新式驗證拓撲、ADAL 和關於新式驗證設定，但是如果您不想這麼做，請參閱以下所需的文章： 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](./topologies-supported.md)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](/skypeforbusiness/manage/authentication/use-adal)
  
新式驗證不只是啟用更安全的驗證方法，例如 Two-Factor 驗證或以憑證為基礎的驗證，只要不需要使用者名稱或密碼，就能對您的使用者執行授權。 這十分實用。

本文將協助您針對商務用 Skype 伺服器上的 (DOS) 攻擊，關閉已受到拒絕服務攻擊的漏洞，方法是將用於驗證的舊方法（從外部、內部或兩者）關閉至您的網路。 例如，協助停用 DOS 攻擊的一個不錯的方法，就是關閉 Windows 整合驗證 (，其中包括 NTLM 和 Kerberos) 。 從外部關閉 NTLM 並依賴憑證型驗證，可協助保護密碼不會洩密。 這是因為 NTLM 會使用密碼認證來驗證使用者，但是由新式驗證啟用憑證型驗證--不是。 這表示降低 DOS 攻擊的一個理想選擇是在外部封鎖 NTLM，而只在這裡使用憑證型驗證。

完全正確，讓我們開始吧。

## <a name="what-would-you-be-changing"></a>您要變更什麼？ 

這些 Cmdlet 適用于存取的 SIP 和 Web 服務點。 雖然這兩個通道使用不同的存取方法，從 NTLM 和 Kerberos 執行 gamut 以匿名存取，但已考慮商務用 Skype 所使用的所有標準方法。

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>如何取得 Get 及 Set-CsAuthConfig Cmdlet

這些指令程式將只會在2018年7月累積更新 (6.0.9319.534) Microsoft 商務用 Skype Server 2015 內安裝，然後您就可以為商務用 Skype 伺服器展開多種拓撲。

## <a name="topologies"></a>拓撲

請務必記住，此案例中包含的支援拓撲是必要的！ 例如，如果您需要尋求協助，以協助封鎖方法，您必須在下列類型之間進行設定。 

> [!IMPORTANT]
> 在下清單格和描述中，*新式驗證* 會縮寫為 __MA__ ， *Windows 整合驗證* 是一種 __入選__ 的縮寫。 如提醒，Windows 整合驗證由兩個方法組成： NTLM 和 Kerberos 驗證。 您將需要知道這一點才能正確讀取資料表！


|       |外部  |內部  |參數  |
|---------|:---------|:---------|---------|
|__類型 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__類型 2__   |  馬       | MA + Win         | BlockWindowsAuthExternally        |
|__類型 3__   |  馬       | 馬        | BlockWindowsAuthExternallyAndInternally        |
|__類型4__   |  馬       | 贏得        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__類型5__   |  MA + Win       | 贏得        | BlockModernAuthInternally         |

__類型1描述：__ 此為 __商務用 Skype Server 開啟 MA 的預設__ 案例。 換句話說，這是設定 MA 的 *起始點* 。

__Type 2 Description：__ 此拓撲會在 *外部* 封鎖 ntlm，但是允許不支援 ADAL) 之用戶端的 Ntlm 或 Kerberos (*在內部* 運作。 如果您的用戶端支援 ADAL，他們會在內部使用 MA。

__類型3描述：__ 此拓撲要求所有使用者 MA。 所有支援 ADAL 功能的用戶端都會在此拓撲中運作，而不會利用密碼（例如，您關閉使用以憑證為基礎的驗證）。

__類型4描述：__ 此拓撲會在內部 *從外部* 封鎖 NTLM，並在內部封鎖 MA。 它可讓 *所有用戶端**在內部* 使用舊版驗證方法， (甚至具備 ADAL 功能的用戶端) 。

__Type 5 Description：__ *對外*，您的現代 ADAL 用戶端將使用 MA，任何不支援 ADAL 的用戶端都會使用舊版驗證方法。 不過， *在內部*， *所有用戶端* 都會使用舊版驗證 (包括所有支援 ADAL 功能的用戶端) 。

在可用選項中追蹤密碼保護的目的相當簡單。 請記住，理想的情況是使用 MA 外部 (例如，透過設定憑證型驗證) ，避免 DOS 攻擊。 如果您是在您的現代用戶端內部利用這種方式，您也會進一步對您的網路進行有關商務用 Skype Server DOS 攻擊的證據。

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>在全域層級使用 Set-CsAuthConfig 的原因

`Set-CsAuthConfig`註冊機構和 Web 服務角色上的指令 Cmdlet 效果設定。

此 Cmdlet 應該在商務用 Skype 伺服器的全域層級執行。 它 *可以* 在集區層級執行，但 *不建議使用* ，因為這會增加安裝的複雜性。 在集區層級執行下列命令，如果您的集區沒有所有的角色包含 (例如，它沒有) 的 Web 服務，將只會針對註冊機構角色設定設定。 在此情況下，Web 服務會使用來自全域層級的設定，這可能是令人困惑的行為 (尤其是在無意中) 時執行。

如果用戶端使用來自某個集區的註冊器設定，以及另一個集區的 Web 服務設定，且驗證設定處於不一致的狀態，yous 用戶端可能無法登入。

此外，如果集區只有一個角色存在： 
* Set-只會設定對應至存在之角色的設定。 因為 *未* 設定某些設定，所以不會提供任何特殊的警告。 
* Get-會傳回對應至存在之角色的設定，以及不存在之角色的全域設定。
* 如果集區的角色都不存在，則無論是 Set 和 Get，都將會傳回錯誤訊息。
* 如果集區的兩個角色都存在，但沒有在集區層級定義原則，則 Get 會傳回錯誤訊息。

它可能會 wisest，以取得這些值，並在進行任何變更之前，以螢幕擷取畫面或記錄其開始狀態。 您也可以考慮保留 OneNote 中的變更記錄。

> [!NOTE]
> 
> 附注：設定 CsAuthConfig 後，您必須在每一部電腦上執行 Enable-CsComputer，使設定生效。

> [!IMPORTANT]
> 如果您使用的是 Lync Web Access (LWA) ，且必須使用以表單為基礎的 Access (FBA) 以進行外部存取，請重新設定 LWA，讓用戶端可以透過匿名存取來存取，以支援這些案例。 同樣地，如果您使用電話撥入式 Pin 碼，將只會封鎖外部使用者的 FBA。 如果他們需要變更其 pin 碼，則必須在內部登入他們的公司以執行此動作。

> [!NOTE]
> 
> 如果您使用 BlockWindowsAuthExternally 參數對外封鎖 NTLM，請注意，這也會在內部為 SIP 通道封鎖 NTLM。 不過，如果商務用 Skype 和 Lync 用戶端的版本超過2010，將仍可登入，因為他們會使用 NTLM over HTTP 登入，並在內部登入憑證，以透過 SIP 登入。 不過，低於2010的用戶端在此情況下將無法在內部登入，而且您可能想要考慮升級這些應用程式，讓使用者能夠繼續安全運作。

> [!IMPORTANT] 
> 有些商務用 Skype web 應用程式不支援 MA。 所以，使用 BlockWindowsAuthExternallyAndInternally 案例時，您將無法存取這些應用程式。 沒有 MA 支援的應用程式是 Web 排程器、Dial-In 頁面、商務用 Skype 控制台 (CSCP) 及回應群組設定] 頁面。 

## <a name="links"></a>連結 
- 如需詳細 PowerShell 資訊：
    -  [CsAuthConfig](/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [CsAuthConfig](/powershell/module/skype/set-csauthconfig?view=skype-ps)

- 如需如何使用命令或執行安裝所需之 CU 的相關指導：
    - [Cmdlet 簡報](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [商務用 Skype Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) (一般) 的更新
    - [2018 年7月商務用 Skype Server 2015，核心元件 CU](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534) 


