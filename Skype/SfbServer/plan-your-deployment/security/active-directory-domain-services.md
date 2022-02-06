---
title: 商務用 Skype Server 的 Active Directory 網域服務
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Active Directory 網域服務可充當 Windows Server 2003 的目錄服務，Windows Server 2008，Windows Server 2012，及 Windows Server 2012 R2 網路。 Active Directory 網域服務也充當建立商務用 Skype Server 安全性基礎結構的基礎。 本節的目的是說明商務用 Skype Server 如何使用 Active Directory 網域服務，為 IM、Web 會議、媒體及語音建立信任的環境。 如需為 Active Directory 網域服務準備環境的詳細資訊，請參閱部署檔中的 Install 商務用 Skype Server。 如需 Windows Server 網路中之 Active Directory 網域服務角色的詳細資料，請參閱您所使用之作業系統版本的文件。
---

# <a name="active-directory-domain-services-for-skype-for-business-server"></a>商務用 Skype Server 的 Active Directory 網域服務
 
Active Directory 網域服務可充當 Windows Server 2003 的目錄服務，Windows Server 2008，Windows Server 2012，及 Windows Server 2012 R2 網路。 Active Directory 網域服務也充當建立商務用 Skype Server 安全性基礎結構的基礎。 本節的目的是說明商務用 Skype Server 如何使用 Active Directory 網域服務，為 IM、Web 會議、媒體及語音建立信任的環境。 如需為 Active Directory 網域服務準備環境的詳細資訊，請參閱部署檔中的[Install 商務用 Skype Server](../../deploy/install/install.md) 。 如需 Windows Server 網路中之 Active Directory 網域服務角色的詳細資料，請參閱您所使用之作業系統版本的文件。
  
商務用 Skype Server 使用 Active Directory 網域服務來儲存：
  
- 樹系中商務用 Skype Server 執行的所有伺服器都需要的全域設定。
    
- 識別樹系中商務用 Skype Server 所有執行之伺服器之角色的服務資訊。
    
- 一些使用者設定。
    
## <a name="active-directory-infrastructure"></a>Active Directory 基礎結構

Active Directory 的基礎結構需求如下：
  
- 網域控制站的作業系統需求
    
- 網域和樹系功能等級需求
    
- 通用類別目錄網域需求
    
如需詳細資訊，請參閱商務用 Skype Server 2019 商務用 Skype Server 2015 或[伺服器需求](../../../SfBServer2019/plan/system-requirements.md)的[環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。
  
## <a name="universal-groups"></a>萬用群組

在準備樹系的過程中，商務用 Skype Server 會在 Active Directory 網域服務中建立各種通用群組，而這些群組具有存取及管理全域設定和服務的許可權。 這些萬用群組包括：
  
- **系統管理群組**。 這些群組會定義商務用 Skype Server 網路的基礎系統管理員角色。 在樹系準備過程中，會將這些系統管理員群組加入商務用 Skype Server 基礎結構群組。
    
- **服務群組**。 這些群組是存取商務用 Skype Server 所提供之各種服務所需的服務帳戶。
    
- **基礎結構群組**。 這些群組提供存取商務用 Skype Server 基礎結構特定區域的許可權。 其功能就如系統管理群組的元件，因此您不應修改這些群組或直接將使用者新增到其中。 在樹系準備過程中，會將特定服務和管理群組新增至適當的基礎結構群組。
    
如需在為商務用 Skype Server 準備 AD 時所建立之特定通用群組的詳細資訊，以及新增至基礎結構群組的服務和管理群組，請參閱部署檔[中商務用 Skype Server 的樹系準備所進行的變更](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)。
  
> [!NOTE]
> 商務用 Skype Server 支援 Windows Server 2012 中的通用群組，以及網域控制站的 Windows Server 2003 作業系統。 萬用群組的成員可以包含網域樹或樹系中任何網域的其他群組和帳戶，而且可以將網域樹或樹系中任何網域的權限指派給它。 通用群組支援（結合系統管理員委派）簡化了商務用 Skype Server 部署的管理。 例如，不需要為了讓系統管理員能夠同時管理兩個網域，而將某個網域加入另一個網域。 
  
## <a name="role-based-access-control"></a>角色型存取控制

除了建立泛型服務和管理群組，以及將服務和系統管理群組新增至適當的通用群組以外，樹系準備也會建立 Role-Based 的存取控制 (RBAC) 群組。 如需「樹系準備」所建立之特定 RBAC 群組的詳細資訊，請參閱部署檔[中商務用 Skype Server 的「樹系準備」所做的變更](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)。 如需 RBAC 群組的詳細資訊，請參閱[以角色為基礎的存取控制 (rbac) 商務用 Skype Server](role-based-access-control-rbac.md)。
  
## <a name="access-control-entries-aces-and-inheritance"></a>存取控制項目 (ACE) 及繼承

樹系準備會同時建立私人與公用 ACE，並針對其建立的萬用群組新增 ACE。 它會在商務用 Skype Server 所使用的全域設定容器上建立特定的專用 ace。 這個容器只會由商務用 Skype Server 使用，而且可以位於根域的設定容器或系統容器中，視您儲存全域設定的位置而定。
  
網域準備步驟會將必要的存取控制項目 (ACE) 新增至萬用群組，而這些群組會授與權限來裝載和管理網域內的使用者。網域準備作業會在網域根目錄和三個內建容器上建立 ACE：使用者、電腦和網域控制站。
  
如需由樹系準備和網域準備所建立及新增之公用 ace 的詳細資訊，請參閱商務用 Skype Server 中的「[樹系準備](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)」所做的變更，以及部署檔中商務用 Skype Server 的[網域準備工作中](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md)所做的變更。
  
組織經常會鎖定 Active Directory 網域服務 (AD DS)，以減低安全性風險。 不過，鎖定的 Active Directory 環境可以限制商務用 Skype Server 所需的許可權。 其中包括從容器和 OU 移除 ACE，以及停用 User、Contact、InetOrgPerson 或 Computer 物件的權限繼承。 在鎖定的 Active Directory 環境中，必須在需要權限的容器和 OU 上手動設定權限。
  
## <a name="server-information"></a>伺服器資訊

在啟用期間，商務用 Skype Server 會將伺服器資訊發佈至 Active Directory 網域服務中的三個下列位置：
  
- 每個 Active Directory 電腦物件上的服務連線點 (SCP) ，對應至商務用 Skype Server 安裝所在的實體電腦。
    
- **msRTCSIP-Pools** 類別容器中建立的伺服器物件。
    
- 拓撲產生器中指定的受信任伺服器。
    
## <a name="service-connection-points"></a>服務連線點

Active Directory 網域服務中的每個商務用 Skype Server 物件都有一個名為 RTC 服務的 SCP，該 SCP 又包含一些屬性可識別每一部電腦，並指定其所提供的服務。 *ServiceDNSName* 、 *serviceDNSNameType* 、 *serviceClassname* 和 *serviceBindingInformation* 等更為重要的 SCP 屬性。 協力廠商資產管理應用程式可以透過查詢 SCP 屬性，在部署中擷取伺服器資訊。
  
## <a name="active-directory-server-objects"></a>Active Directory 伺服器物件

每個商務用 Skype Server Server role 都有對應的 Active Directory 物件，其屬性可定義該角色所提供的服務。 此外，當您啟用 Standard Edition 伺服器時，或在建立 Enterprise Edition 集區時，商務用 Skype Server 會在 **msRTCSIP-Pools** 容器中建立新的 **msRTCSIP 集** 區物件。 **msRTCSIP-Pool** 類別會指定集區的完整網域名稱 (FQDN)，以及集區前端和後端元件之間的關聯性。 Standard Edition 伺服器會視為邏輯集區，其前端和後端會配置在同一部電腦上。
  
## <a name="trusted-servers"></a>受信任伺服器

在商務用 Skype Server 中，受信任的伺服器是執行拓撲產生器併發行拓撲時所指定的伺服器。 發行的拓撲 (包括所有伺服器資訊) 會儲存在中央管理存放區中。 只有定義在中央管理存放區中的伺服器會受信任。 在商務用 Skype Server 中，信任的伺服器是符合下列條件的伺服器：
  
- 伺服器的 FQDN 出現在儲存於中央管理存放區的拓撲中。
    
- 伺服器顯示來自受信任 CA 的有效憑證。 如需詳細資訊，請參閱[商務用 Skype Server 2015 的環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)，或[商務用 Skype Server 2019 的系統需求](../../../SfBServer2019/plan/system-requirements.md)。
    
如果不符合這些條件，則伺服器就不受信任，其連線也會遭拒。 這種雙重需求可防止惡意伺服器企圖透過有效伺服器的 FQDN 採取的攻擊（如果不太可能）。
  
此外，若要啟用 Microsoft Office 通訊伺服器 2007 R2，並 Microsoft Office 通訊伺服器2007部署與商務用 Skype Server 伺服器進行通訊，商務用 Skype Server 在樹系準備期間建立容器，以存放舊版版本的受信任伺服器清單。 下表說明為與舊版部署相容而建立的容器。
  
**為與舊版相容的受信任伺服器清單及其 Active Directory 容器**

|**受信任的伺服器清單**|**Active Directory 容器**|
|:-----|:-----|
|Standard Edition 伺服器和 Enterprise 集區前端伺服器  <br/> |RTC 服務/通用設定  <br/> |
|會議伺服器  <br/> |RTC 服務/信任的 MCU  <br/> |
|Web 元件伺服器  <br/> |RTC 服務/TrustedWebComponentsServers  <br/> |
|中繼伺服器及 Communicator Web Access Server、應用程式伺服器、含 QoE 的登錄器、A/V 會議服務 (還有協力廠商 SIP 伺服器)  <br/> |RTC 服務/信任的服務  <br/> |
|Proxy 伺服器  <br/> |商務用 Skype Server 不支援 proxy 伺服器的回溯相容性  <br/> |
   

## <a name="see-also"></a>另請參閱

[為商務用 Skype Server 準備 Active Directory](../../deploy/install/prepare-active-directory.md)
