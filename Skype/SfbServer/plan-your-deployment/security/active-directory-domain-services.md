---
title: 商務用 Skype Server 的 Active Directory 網域服務
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
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Active Directory 網域服務的功能是 Windows Server 2003、Windows Server 2008、Windows Server 2012 和 Windows Server 2012 R2 網路的目錄服務。 Active Directory 網域服務也會充當建立商務用 Skype Server 安全基礎結構的基礎。 本節的目的是說明商務用 Skype 伺服器如何使用 Active Directory 網域服務來建立 IM、網路會議、媒體及語音等可信環境。 如需有關為 Active Directory 網域服務準備環境的詳細資訊，請參閱在部署檔中安裝商務用 Skype 伺服器。 如需有關 Windows Server 網路中 Active Directory 網域服務角色的詳細資訊，請參閱您所使用之作業系統版本的相關檔。
ms.openlocfilehash: ec3a09e2203b6f862d87403818b43ab6daae33ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815711"
---
# <a name="active-directory-domain-services-for-skype-for-business-server"></a>商務用 Skype Server 的 Active Directory 網域服務
 
Active Directory 網域服務的功能是 Windows Server 2003、Windows Server 2008、Windows Server 2012 和 Windows Server 2012 R2 網路的目錄服務。 Active Directory 網域服務也會充當建立商務用 Skype Server 安全基礎結構的基礎。 本節的目的是說明商務用 Skype 伺服器如何使用 Active Directory 網域服務來建立 IM、網路會議、媒體及語音等可信環境。 如需有關為 Active Directory 網域服務準備環境的詳細資訊，請參閱在部署檔中[安裝商務用 Skype 伺服器](../../deploy/install/install.md)。 如需有關 Windows Server 網路中 Active Directory 網域服務角色的詳細資訊，請參閱您所使用之作業系統版本的相關檔。
  
商務用 Skype 伺服器使用 Active Directory 網域服務來儲存：
  
- 在樹林中執行商務用 Skype 伺服器的所有伺服器都需要的全域設定。
    
- 服務資訊，可識別在林中執行商務用 Skype Server 的所有伺服器角色。
    
- 部分使用者設定。
    
## <a name="active-directory-infrastructure"></a>Active Directory 基礎結構

Active Directory 的基礎結構需求包括下列各項：
  
- 網網域控制站的作業系統需求
    
- 網域和林功能層級需求
    
- 全域編目網域需求
    
如需詳細資訊，請參閱商務用 skype Server 2015 或[伺服器需要](../../../SfBServer2019/plan/system-requirements.md)的商務用 skype server 2019 的[環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。
  
## <a name="universal-groups"></a>通用群組

在準備林的過程中，商務用 Skype 伺服器會在 Active Directory 網域服務中建立可存取及管理全域設定及服務許可權的各種通用群組。 這些通用群組包括：
  
- [系統**管理群組**]。 這些群組會定義商務用 Skype Server 網路的基本系統管理員角色。 在林準備期間，這些系統管理員群組會新增至商務用 Skype Server 基礎結構群組。
    
- **服務群組**。 這些群組是服務帳戶，必須用來存取商務用 Skype Server 提供的各種服務。
    
- **基礎結構群組**。 這些群組提供存取商務用 Skype Server 基礎結構特定區域的許可權。 它們的功能是系統管理群組的元件，您不應該直接修改它們或直接將使用者新增至其中。 在林準備期間，系統會將特定的服務與管理群組新增至適當的基礎結構群組中。
    
如需在準備商務用 Skype Server 的 AD 時所建立的特定通用群組，以及新增至基礎結構群組的服務和管理群組，請參閱在部署檔中的商務用 Skype Server 中的 [[目錄林準備](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)] 所做的變更。
  
> [!NOTE]
> 商務用 Skype 伺服器支援 Windows Server 2012 中的通用群組，以及適用于網網域控制站的 Windows Server 2003 作業系統。 通用群組的成員可以包含網域樹狀結構或林中任何網域的其他群組和帳戶，而且可以在網域樹狀結構或樹林中的任何網域中指派許可權。 通用群組支援（結合管理員委派）簡化了商務用 Skype Server 部署的管理。 例如，您不需要將一個網域新增至另一個網域，就能讓系統管理員同時管理兩者。 
  
## <a name="role-based-access-control"></a>以角色為基礎的存取控制

除了建立泛型服務與管理群組，以及將服務和系統管理群組新增至適當的通用群組之外，林準備也會建立以角色為基礎的存取控制（RBAC）群組。 如需有關林準備所建立之特定 RBAC 群組的詳細資訊，請參閱部署檔中的[商務用 Skype Server 中的林準備所做的變更](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)。 如需 RBAC 群組的詳細資訊，請參閱[商務用 Skype Server 的角色式存取控制（RBAC）](role-based-access-control-rbac.md)。
  
## <a name="access-control-entries-aces-and-inheritance"></a>存取控制專案（Ace）與繼承

林準備會建立私人和公用 Ace，並為它所建立的通用群組新增 Ace。 它會在商務用 Skype Server 所使用的全域設定容器上建立特定的專用 Ace。 這個容器只能由商務用 Skype Server 使用，且位於配置容器或根網域中的系統容器中，視您儲存全域設定的位置而定。
  
[網域準備] 步驟會將必要的存取控制專案（Ace）新增至通用群組，以便在網域中授與主機及管理使用者的許可權。 [網域準備] 會在網域根目錄和三個內建容器中建立 Ace：使用者、電腦及網網域控制站。
  
如需由目錄林準備及網域準備所建立和新增的公用 Ace 的詳細資料，請參閱[在商務](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)用 skype server 的 [商務用 skype] 中由網域準備所做的變更，以及由部署檔中的[商務用 skype server 所做的變更](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md)。
  
組織通常會鎖定 Active Directory 網域服務（AD DS），協助減輕安全性風險。 不過，鎖定的 Active Directory 環境可以限制商務用 Skype Server 所需的許可權。 這可能包括從容器和 Ou 中移除 Ace，以及在使用者、連絡人、InetOrgPerson 或電腦物件上停用許可權繼承。 在鎖定的 Active Directory 環境中，許可權必須在需要它們的容器和 Ou 上手動設定。
  
## <a name="server-information"></a>伺服器資訊

在啟用期間，商務用 Skype 伺服器會將伺服器資訊發佈至 Active Directory 網域服務中的三個位置：
  
- 每個 Active Directory 電腦物件上的服務連接點（SCP），對應到安裝商務用 Skype Server 的物理電腦。
    
- 在**MsRTCSIP 池**類別的容器中建立的伺服器物件。
    
- 在拓撲建立器中指定的信任伺服器。
    
## <a name="service-connection-points"></a>服務連接點

Active Directory 網域服務中的每個商務用 Skype Server 物件都有一個名為「RTC 服務」的 SCP，該 SCP 又包含幾個屬性來識別每個電腦並指定它所提供的服務。 *ServiceDNSName* 、 *serviceDNSNameType* 、 *serviceClassname*和*serviceBindingInformation*等更重要的 SCP 屬性。 協力廠商資產管理應用程式可透過查詢這些與其他 SCP 屬性來在整個部署中檢索伺服器資訊。
  
## <a name="active-directory-server-objects"></a>Active Directory Server 物件

每個商務用 Skype Server 伺服器角色都有對應的 Active Directory 物件，其屬性會定義該角色所提供的服務。 此外，當您啟用標準版伺服器或建立企業版文件庫時，商務用 Skype Server 會在 MsRTCSIP 的 [**池**] 容器中建立新的**msRTCSIP 池**物件。 **MsRTCSIP 池**類別指定了池子的完整功能變數名稱（FQDN），以及該池前端與後端元件之間的關聯。 （標準版伺服器會被視為在單一電腦上 collocated 其前端和後端的邏輯池）。
  
## <a name="trusted-servers"></a>受信任的伺服器

在商務用 Skype Server 中，受信任的伺服器是在您執行拓撲建立器併發布拓撲時指定的伺服器。 已發佈的拓撲（包括所有伺服器資訊）都儲存在中央管理儲存區中。 只有在中央管理存儲區中定義的伺服器才是受信任的。 在商務用 Skype Server 中，信任的伺服器是符合下列準則的伺服器：
  
- 伺服器的 FQDN 會出現在儲存在中央管理存放區的拓撲中。
    
- 伺服器會從信任的 CA 中出示有效的憑證。 如需詳細資訊，請參閱商務用 skype server [2015 的環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)，或[商務用 skype Server 2019 的系統需求](../../../SfBServer2019/plan/system-requirements.md)。
    
如果缺少其中一個準則，則伺服器不受信任，且無法與它連線。 這種雙重需求可以避免可能的情況下，惡意伺服器企圖利用有效伺服器的 FQDN 來取得的攻擊。
  
此外，若要啟用 Microsoft Office 通訊伺服器 2007 R2 和 Microsoft Office 通訊伺服器2007部署，以便與商務用 Skype 伺服器伺服器進行通訊，商務用 Skype 伺服器會在林準備期間建立容器針對先前的版本，請保留受信任伺服器的清單。 下表說明為啟用與舊版部署相容性而建立的容器。
  
**受信任的伺服器清單及其 Active Directory 容器，以與舊版版本相容**

|**受信任的伺服器清單**|**Active Directory 容器**|
|:-----|:-----|
|標準版伺服器與企業版池前端伺服器  <br/> |RTC 服務/全域設定  <br/> |
|會議服務器  <br/> |RTC 服務/信任的 MCUs  <br/> |
|網頁元件伺服器  <br/> |RTC 服務/TrustedWebComponentsServers  <br/> |
|中繼伺服器與 Communicator Web Access 伺服器、應用程式伺服器、QoE 的註冊機構、A/V 會議服務（也是協力廠商 SIP 伺服器）  <br/> |RTC 服務/受信任的服務  <br/> |
|Proxy 伺服器  <br/> |商務用 Skype 伺服器不支援 proxy 伺服器的向後相容性  <br/> |
   

## <a name="see-also"></a>另請參閱

[為商務用 Skype Server 準備 Active Directory](../../deploy/install/prepare-active-directory.md)
