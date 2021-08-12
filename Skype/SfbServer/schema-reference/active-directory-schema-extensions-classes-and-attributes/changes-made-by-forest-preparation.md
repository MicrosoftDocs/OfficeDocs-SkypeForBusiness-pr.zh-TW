---
title: 商務用 Skype Server 中的樹系準備所進行的變更
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: 本節將說明樹系準備步驟所建立的全域設定與物件，以及萬用服務和管理群組。
ms.openlocfilehash: 8a613b4f71d26f06d36543ef4ec10dab39442860b0435ccd84417624d495c9fe
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349725"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>商務用 Skype Server 中的樹系準備所進行的變更

本節將說明樹系準備步驟所建立的全域設定與物件，以及萬用服務和管理群組。

## <a name="active-directory-global-settings-and-objects"></a>Active Directory 全域設定和物件

如果您將全域設定儲存在設定容器中 (所有新的商務用 Skype Server 部署) 的情況下，樹系準備會使用現有的服務容器，並在 Configuration\Services 物件底下新增 **RTC 服務** 物件。 在 RTC 服務物件下，樹系準備會新增 msRTCSIP-GlobalContainer 類型的 **Global Settings** 物件。 全域設定物件會包含套用至商務用 Skype Server 部署的所有設定。 如果您將全域設定儲存在「系統」容器中，則樹系準備會使用根網域「系統」容器下的 Microsoft 容器，並在 System\Microsoft 物件下新增 RTC 服務物件。

樹系準備也會針對執行程序的根網域，新增 **msRTCSIP-Domain** 物件。

## <a name="active-directory-universal-service-and-administration-groups"></a>Active Directory 萬用服務和管理群組

樹系準備也會根據您指定的網域建立萬用群組，並為這些群組新增存取控制項目 (ACE)。這個步驟會在您指定之網域的使用者容器中，建立萬用群組。

萬用群組允許管理員存取以及管理全域設定和服務。樹系準備會新增下列類型的萬用群組：

- 系統 **管理群組** 這些群組會為商務用 Skype Server 網路定義系統管理員角色。

- **基礎結構群組** 這些群組提供存取商務用 Skype Server 基礎結構特定區域的許可權。 它們可做為系統管理群組元件的功能來運作。 您不應該修改這些群組或將使用者直接新增至這些群組中。

- **服務群組** 這些群組是存取各種商務用 Skype Server 服務所需的服務帳戶。

下表說明系統管理群組。

**樹系準備時建立的系統管理群組**

|**系統管理群組**|**描述**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |允許成員管理伺服器和集區設定，包括所有伺服器角色、全域設定以及使用者。  <br/> |
|RTCUniversalUserAdmins  <br/> |可讓成員管理使用者設定，也可以將使用者從一個伺服器或集區移到另一個伺服器或集區。  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |可讓成員讀取伺服器、集區和使用者設定。  <br/> |

下表說明基礎結構群組。

**樹系準備時建立的基礎結構群組**

|**基礎結構群組**|**描述**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |授與商務用 Skype Server 之全域設定物件的寫入權限。  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |授與商務用 Skype Server 之全域設定物件的唯讀存取權。  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |授與商務用 Skype Server 使用者設定的唯讀許可權。  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |授與商務用 Skype Server 設定的唯讀存取權。 這個群組沒有集區層級設定的存取權，只能存取個別伺服器特有的設定。  <br/> |
|RTCUniversalSBATechnicians  <br/> |授與商務用 Skype Server 設定的唯讀存取權，並將其放置在安裝期間 survivable 分支裝置的本機系統管理員群組中。  <br/> |

下表說明服務群組。

**樹系準備時建立的服務群組**

|**服務群組**|**描述**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |包含用於執行前端伺服器及 Standard Edition 伺服器的服務帳戶。 這個群組可讓伺服器可讀取/寫入存取商務用 Skype Server 通用設定和 Active Directory 使用者物件。  <br/> |
|RTCComponentUniversalServices  <br/> |包括用來執行 A/V 會議伺服器、Web 服務、轉送伺服器、封存伺服器及監控伺服器的服務帳戶。  <br/> |
|RTCProxyUniversalServices  <br/> |包含用來執行商務用 Skype Server Edge server 的服務帳戶。  <br/> |
|RTCUniversalConfigReplicator  <br/> |包括可參與商務用 Skype Server 中央管理存放區複寫的伺服器。  <br/> |
|RTCSBAUniversalServices  <br/> |授與商務用 Skype Server 設定的唯讀存取權，但允許設定 survivable branch Server 和 survivable branch 裝置部署的安裝。  <br/> |

接著，樹系準備會將服務和管理群組新增到適當的基礎結構群組，如下所示：

- 新增 RTCUniversalServerAdmins 到 RTCUniversalGlobalReadOnlyGroup、RTCUniversalGlobalWriteGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup。

- 新增 RTCUniversalUserAdmins 做為 RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成員。

- 新增 RTCHSUniversalServices、RTCComponentUniversalServices 和 RTCUniversalReadOnlyAdmins 做為 RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成員。

樹系準備也會建立下列角色型存取控制 (RBAC) 群組：

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

如需 RBAC 角色以及各角色可執行的工作的詳細資訊，請參閱規劃文件中的＜[Role-Based Access Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control)＞。

樹系準備會同時建立私人與公用 ACE。 它會在商務用 Skype Server 所使用的全域設定容器上建立專用 ace。 這個容器只會由商務用 Skype Server 使用，而且可以位於根域的設定容器或系統容器中，視您儲存全域設定的位置而定。 樹系準備所建立的公用 ACE 列於下表。

**樹系準備建立的公用 ACE。**


| **Ace**                                                                 | **RTCUniversalGlobalReadOnlyGroup** |
|:------------------------------------------------------------------------|:------------------------------------|
| 讀取根網域系統容器 (未繼承) **\\**\* <br/>        | X  <br/>                            |
| 未繼承讀取設定的 DisplaySpecifiers 容器 ()   <br/> | X  <br/>                            |

> [!NOTE]
> <strong>\\</strong>* 未繼承的 Ace 不會將存取權授與這些容器底下的子物件。 繼承的 Ace 會將存取權授與這些容器底下的子物件。

樹系準備會在組態命名內容下的設定容器上執行下列工作：

- 在使用者、連絡人和 InetOrgPerson 之語言顯示規範的 adminContextMenu 和 adminPropertyPages 屬性下方，為 **RTC property** 頁面新增 **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** 項目 (例如 CN=user-Display、CN=409、CN=DisplaySpecifiers)。

- 在套用到 User 和 Contact 類別的 **Extended-Rights** 下方，新增 **controlAccessRight** 類型的 **RTCPropertySet** 物件。

- 在套用到 User、Contact、OU 與 DomainDNS 類別的 **Extended-Rights** 下方，新增 **controlAccessRight** 類型的 **RTCUserSearchPropertySet** 物件。

- 在每一個語言組織單位 (OU) 顯示規範 (例如，CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) 的 **extraColumns** 屬性下新增 **msRTCSIP-PrimaryUserAddress**，並複製預設顯示 (例如，CN=default-Display、CN=409、CN=DisplaySpecifiers) 的 **extraColumns** 屬性值。

- 在 Users、Contacts 與 InetOrgPerson 物件的每一個語言顯示規範的 **attributeDisplayNames** 屬性下，新增 **msRTCSIP-PrimaryUserAddress**、**msRTCSIP-PrimaryHomeServer** 與 **msRTCSIP-UserEnabled** 篩選屬性 (以英文為例：CN=user-Display、CN=409、CN=DisplaySpecifiers)。