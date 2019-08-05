---
title: 在商務用 Skype Server 的 [目錄林準備] 中所做的變更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: 本節說明全域設定與物件, 以及由目錄林準備步驟所建立的泛型服務和管理群組。
ms.openlocfilehash: ece4a9bd1db5f43b52a96265dee41ee3a0a30b22
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192923"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>在商務用 Skype Server 的 [目錄林準備] 中所做的變更

本節說明全域設定與物件, 以及由目錄林準備步驟所建立的泛型服務和管理群組。

## <a name="active-directory-global-settings-and-objects"></a>Active Directory 全域設定與物件

如果您在配置容器中儲存全域設定 (所有新的商務用 Skype 伺服器部署都一樣), 目錄林準備就會使用現有的服務容器, 並在 Configuration\Services 下新增**RTC 服務**物件。面向. 在 RTC 服務物件下, 林準備會新增 type msRTCSIP-GlobalContainer 的**全域設定**物件。 [全域設定] 物件包含所有適用于商務用 Skype Server 部署的設定。 如果您在系統容器中儲存全域設定, 目錄林準備會在 System\Microsoft 物件的根網域系統容器和 RTC 服務物件下使用 Microsoft 容器。

林準備也會為執行程式的根網域新增一個新**的 msRTCSIP-網域**物件。

## <a name="active-directory-universal-service-and-administration-groups"></a>Active Directory 泛型服務與管理群組

林準備會根據您指定的網域建立通用群組, 並新增這些群組的存取控制專案 (Ace)。 此步驟會在您指定之網域的使用者容器中建立通用群組。

通用群組可讓系統管理員存取及管理全域設定及服務。 [林準備] 會新增下列類型的通用群組:

- 系統**管理群組**這些群組會定義商務用 Skype Server 網路的系統管理員角色。

- **基礎結構群組**這些群組提供存取商務用 Skype Server 基礎結構特定區域的許可權。 它們的功能是系統管理群組的元件。 您不應該修改這些群組, 或直接將使用者新增至其中。

- **服務群組**這些群組是存取各種商務用 Skype Server 服務所需的服務帳戶。

下表說明管理群組。

**在林準備期間建立的系統管理群組**

|**系統管理群組**|**說明**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |允許成員管理伺服器和池設定, 包括所有伺服器角色、全域設定和使用者。  <br/> |
|RTCUniversalUserAdmins  <br/> |允許成員管理使用者設定, 以及將使用者從一個伺服器或一個池移到另一個伺服器或資源庫。  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |允許成員讀取伺服器、池及使用者設定。  <br/> |

下表說明基礎結構群組。

**在林準備期間建立的基礎結構群組**

|**基礎結構群組**|**說明**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |授與商務用 Skype Server 全域設定物件的寫入權限。  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |授與商務用 Skype Server 全域設定物件的唯讀存取權。  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |授與商務用 Skype Server 使用者設定的唯讀存取權。  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |授與商務用 Skype Server 設定的唯讀存取權。 這個群組無法存取 [池] 層級設定, 只適用于個別伺服器專用的設定。  <br/> |
|RTCUniversalSBATechnicians  <br/> |授與商務用 Skype Server 設定的唯讀存取權, 並放在安裝期間 survivable 分支裝置的 [本機管理員] 群組中。  <br/> |

下表說明服務群組。

**在林準備期間建立的服務群組**

|**服務群組**|**說明**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |包含用來執行前端伺服器和標準版伺服器的服務帳戶。 這個群組可讓伺服器讀/寫商務用 Skype Server 全域設定和 Active Directory 使用者物件的存取權。  <br/> |
|RTCComponentUniversalServices  <br/> |包含用來執行 A/V 會議伺服器、Web 服務、中繼伺服器、封存伺服器及監視伺服器的服務帳戶。  <br/> |
|RTCProxyUniversalServices  <br/> |包含用來執行商務用 Skype Server Edge 伺服器的服務帳戶。  <br/> |
|RTCUniversalConfigReplicator  <br/> |包括可參與商務用 Skype Server 中央管理儲存複製的伺服器。  <br/> |
|RTCSBAUniversalServices  <br/> |授與商務用 Skype Server 設定的唯讀存取權, 但允許安裝 survivable 分支伺服器和 survivable 分支裝置部署。  <br/> |

[林準備] 接著會將服務和系統管理群組新增至適當的基礎結構群組, 如下所示:

- RTCUniversalServerAdmins 已新增至 RTCUniversalGlobalReadOnlyGroup、RTCUniversalGlobalWriteGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup。

- RTCUniversalUserAdmins 會新增為 RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成員。

- RTCHSUniversalServices、RTCComponentUniversalServices 和 RTCUniversalReadOnlyAdmins 會新增為 RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成員。

林準備也會建立下列角色式存取控制 (RBAC) 群組:

- CSAdministrator

- CSArchivingAdministrator

- CSHelpDesk

- CSLocationAdministrator

- CSResponseGroupAdministrator

- CSServerAdministrator

- CSUserAdministrator

- CSViewOnlyAdministrator

- CSVoiceAdministrator

- CsPersistentChatAdministator

- CsResponseGroupManager

如需 RBAC 角色及每個角色所允許的工作的詳細資訊, 請參閱規劃檔中的[角色式存取控制](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)。

林準備會建立私人和公用 Ace。 它會在商務用 Skype Server 所使用的全域設定容器上建立私用 Ace。 這個容器只能由商務用 Skype Server 使用, 且位於配置容器或根網域中的系統容器中, 視您儲存全域設定的位置而定。 [林準備] 建立的公用 Ace 列在下表中。

**由林準備建立的公用 Ace**


| **A**                                                                 | **RTCUniversalGlobalReadOnlyGroup** |
|:------------------------------------------------------------------------|:------------------------------------|
| 讀取根網域系統容器 (不繼承)**\\**\* <br/>        | X  <br/>                            |
| 讀取配置的 DisplaySpecifiers 容器 (不是繼承的)  <br/> | X  <br/>                            |

> [!NOTE]
> <strong>\\</strong>* 沒有繼承的 Ace 不會在這些容器下授與子物件的存取權。 被繼承的 Ace 在這些容器下授與子物件的存取權。

在 [設定] 容器的 [設定命名] 內容底下, [林準備] 會執行下列任務:

- 針對使用者、連絡人和 InetOrgPersons (例如 CN = AB255F23-2DBD-4bb6-891D-38754AC280EF) 的語言顯示說明符之 [adminCoNtextMenu] 和 [adminPropertyPages] 屬性, 在 [ **RTC] 屬性**頁面上新增專案 **{}** 使用者顯示, CN = 409, CN = DisplaySpecifiers)。

- 在套用至使用者和連絡人類別的**延伸許可權**底下, 新增類型**controlAccessRight**的**RTCPropertySet**物件。

- 在適用于使用者、連絡人、OU 和 DomainDNS 類別的**延伸許可權**底下, 新增類型**controlAccessRight**的**RTCUserSearchPropertySet**物件。

- 在每個語言組織單位 (OU) 顯示說明符的**extraColumns**屬性 (例如, Cn = OrganizationalUnit-DISPLAY、cn = 409、Cn = DisplaySpecifiers) 下新增**msRTCSIP-PrimaryUserAddress** , 並將其值複製預設顯示的**extraColumns**屬性 (例如, cn = 預設顯示, cn = 409, Cn = DisplaySpecifiers)。

- 將**msRTCSIP-PrimaryUserAddress**、 **msRTCSIP-PrimaryHomeServer**及**msRTCSIP-UserEnabled**篩選屬性新增至每個語言顯示指定符的**AttributeDisplayNames**屬性, 以供使用者、連絡人、InetOrgPerson 物件 (例如英文): CN = 使用者顯示, CN = 409, CN = DisplaySpecifiers)。


