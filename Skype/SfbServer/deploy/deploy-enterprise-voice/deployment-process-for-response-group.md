---
title: 商務用 Skype 中回應群組的部署程式
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: 商務用 Skype Server 企業語音中的回應群組部署程式與步驟。
ms.openlocfilehash: cbc8a26e88cc98f32042ba00fab1ecf181af67d4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765871"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>商務用 Skype 中回應群組的部署程式

商務用 Skype Server 企業語音中的回應群組部署程式與步驟。

回應群組是一種企業語音功能，可將來電路由及列隊給一組人（稱為「服務台」，例如「服務台」或「客戶服務台」）。

「回應群組」所需的元件，會在您部署企業語音時自動安裝於前端伺服器或 Standard Edition Server 上並啟用。 若要讓使用者能夠使用「回應群組」，您必須依序設定專員群組、佇列和工作流程。 此外，回應群組管理員可以將現有工作流程的設定委派給回應群組管理員，然後該管理員可以修改及重新設定工作流程及其相關聯的代理人群組和佇列。

若要設定回應群組，您至少必須是下列其中一個系統管理角色的成員：

|**Active Directory 安全性群組 (1)** <br/> |建立工作流程  <br/> |指派管理員  <br/> |建立/指派代理人和佇列  <br/> |建立/管理假日和營業時間  <br/> |啟用/停用工作流程  <br/> |設定工作流程 (IVR 或群組搜尋)  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**CsResponseGroupAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsResponseGroupManager** <br/> ||√ (2)   <br/> |√ (3)   <br/> |√ (3)   <br/> |√ (3)   <br/> |√ (3)   <br/> |
|**CsVoiceAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsServerAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsViewOnlyAdministrator** <br/> |√ (4)   <br/> |√ (4)   <br/> |√ (4)   <br/> |√ (4)   <br/> |√ (4)   <br/> |√ (4)   <br/> |

> [!NOTE]
> **(1)** Active Directory 網域服務使用者物件必須是所列指定之 Active Directory 安全性群組的成員。 具有適當許可權的系統管理員或其他委派的 Active Directory 群組成員，可將使用者新增至安全性群組中 (例如，系統管理員、帳戶操作員) 必須將使用者物件新增至所列的安全性群組或群組，使用者才能執行所列的功能。 **(2)** 僅適用于 CsResponseGroupAdministrator 已指定給 CsResponseGroupManager 的工作流程。 **(3)** 回應群組管理員可以將 CsResponseGroupManager 的另一個成員指派給目前管理員已管理的工作流程。 **(4)** CsViewOnlyAdministrator 只能執行動詞 "Get" Cmdlet。

## <a name="response-group-configuration-prerequisites"></a>回應群組設定先決條件

回應群組需要下列元件：

- 應用程式服務

- 回應群組應用程式

- 語言套件

- 檔案存放區 (用於保留音訊檔案)

- Web 服務 (包含回應群組設定工具和代理程式的登入和登出主控台) 

當您部署企業語音時，預設會安裝上述所有元件。

在設定回應群組之前，您可能需要先執行下列工作：

- 為使用者啟用 Lync Server 2013 和企業語音。

- 修改組態檔，以符合美國聯邦資訊處理標準 (FIPS)。

- 修改資料庫定序，以支援佇列名稱和代理人群組名稱中的 Yi、Meng 和 Zang 字元。

### <a name="enabling-users"></a>啟用使用者

設定回應群組的第一個步驟是建立代理人群組。 在您可以建立代理人群組之前，您必須啟用商務用 Skype 和企業語音的回應群組之代理人的使用者。 為商務用 Skype 啟用使用者通常是 Enterprise Edition 伺服器或 Standard Edition 伺服器部署的步驟。 如需為商務用 Skype 啟用使用者的詳細資訊，請參閱[啟用或停用使用者的 Lync Server 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server)。 啟用使用者的企業語音一般是企業語音部署中的步驟。 如需詳細資訊，請參閱在[商務用 Skype Server 中啟用企業語音的使用者](enable-users-for-enterprise-voice.md)。

### <a name="complying-with-fips-requirements"></a>遵守 FIPS 要求

只有在您的組織需要遵守美國聯邦資訊處理標準 (FIPS) 時，才適用本節內容。

若要遵守 FIPS，您需要修改應用程式層級的 Web.config 檔案，以在安裝 Web 服務後使用不同的密碼編譯演算法。 您需要指定 ASP.NET 使用三重資料加密標準 (3DES) 演算法來處理檢視狀態資料。 針對回應群組應用程式，此需求適用于回應群組設定工具和代理程式登入和登出主控台。

若要修改 Web.config 檔案，請執行下列動作：

1. 在文字編輯器 (如 [記事本]) 中，開啟應用程式層級的 Web.config 檔案。

2. 在 Web.config 檔案中，找出  `<system.web>` 區段。

3. `<machineKey>`在區段中新增下列區段 `<system.web>` ：

   ```xml
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. 儲存 Web.config 檔案。

5. 在命令提示字元中執行下列命令，以重新開機 Internet Information Services (IIS) 服務：

   ```console
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>支援 Yi、Meng 和 Zang 字元

只有在您的組織需要支援 Yi、Meng 或 Zang 字元時，才適用本節內容。

> [!NOTE]
> 如需有關彝語、Meng 及 Zang 字元的資訊及其可能對您的部署很重要的原因，請參閱 GB18030 字元集上的資訊 [https://go.microsoft.com/fwlink/p/?linkId=240223](/previous-versions/sql/sql-server-2008-r2/ms180991(v=sql.105)) 。

若要支援 Yi、Meng 或 Zang 字元，您需要修改 Rgsconfig 資料庫的定序。請變更每個 Rgsconfig 資料庫中下列各資料表內 **[名稱]** 資料行的定序：

- Dbo。AgentGroups

- Dbo。BusinessHours

- Dbo。HolidaySets

- Dbo。佇列

- Dbo。流程

若為 SQL Server 2008 R2 和 SQL Server 2012，請使用 Latin_General_100 (區分重音) 歸類。 如果您使用此定序，則所有物件名稱都不區分大小寫。

您可以使用 Microsoft SQL Server Management Studio 來變更定序。 如需使用此工具的詳細資訊，請參閱「[使用 SQL Server Management Studio](/sql/ssms/sql-server-management-studio-ssms)」。 請遵循下列步驟來變更定序：

1. 確定 SQL Server Management Studio 已設成允許需要重建資料表的變更。 如需詳細資訊，請參閱「 [不允許) 的儲存 (] 對話方塊](/sql/ssms/visual-db-tools/save-not-permitted-dialog-box)。 如需設定欄歸類的詳細資訊，請參閱 how [to： Set Column 歸類 (Visual Database Tools) "](/previous-versions/sql/sql-server-2008-r2/ms187473(v=sql.105))。

2. 使用 Microsoft SQL Server Management Studio 連線至 Rgsconfig 資料庫。

3. 在 Rgsconfig 資料庫中找到想要變更的資料表，並用滑鼠右鍵按一下資料表，然後按一下 **[設計]**。

4. 變更 **[名稱]** 資料行的定序，然後儲存資料表。

## <a name="response-group-deployment-steps"></a>回應群組的部署步驟

**回應群組部署程式**

|**階段**|**步驟**|**權限**|**部署文件**|
|:-----|:-----|:-----|:-----|
|為使用者啟用商務用 Skype 和企業語音  <br/> |啟用將負責商務用 Skype 和企業語音之代理人的使用者。 您必須先啟用使用者，才能將其新增至代理人群組。 通常在 Enterprise Edition 或 Standard Edition 伺服器部署期間為使用者啟用商務用 Skype。 在部署企業語音期間為使用者啟用企業語音。  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[啟用或停用使用者的 Lync Server 2013 預覽](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server) <br/> [在商務用 Skype Server 中為使用者啟用企業語音](enable-users-for-enterprise-voice.md) <br/> |
|建立和設定回應群組，包括代理群組、佇列和工作流程  <br/> |1. 使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面執行下列作業：  <br/> a. 建立和設定代理人群組。  <br/> b. 建立和設定佇列。  <br/> 2. 使用商務用 Skype Server 管理命令介面來建立預先定義的回應群組上班時間與假日。  <br/> 3. 使用回應群組設定工具或商務用 Skype Server 管理命令介面，來建立工作流程 (群組搜尋或互動語音回應 (IVR) 通話流程) ，包括自訂回應群組上班時間與假日。  <br/> 您可以透過商務用 Skype Server 控制台] 來存取回應群組設定工具。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[建立回應群組代理群組](/previous-versions/office/lync-server-2013/lync-server-2013-create-response-group-agent-groups) <br/> [建立回應群組佇列](/previous-versions/office/lync-server-2013/lync-server-2013-create-response-group-queues) <br/> [ (選用) 在商務用 Skype 中定義回應群組上班時間](optional-define-response-group-business-hours.md) <br/> [ (選用) 定義回應群組假日集商務用 Skype](optional-define-response-group-holiday-sets.md) <br/> [在商務用 Skype 中設計及建立回應群組工作流程](designing-and-creating-response-group-workflows.md) <br/> |
| (選用) 自訂應用層級設定  <br/> |使用商務用 Skype Server 管理命令介面，來自訂預設的等候音樂設定、預設的等候音樂音訊檔、代理程式回電寬限時間，以及呼叫內容設定。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype 中管理應用層級回應群組設定](managing-application-level-response-group-settings.md) <br/> |
| (選用) 委派管理回應群組  <br/> |將 CsResponseGroupManager 角色指派給使用者，以委派回應群組的設定。 然後，回應群組管理員可以設定指派給他們的回應群組。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[規劃角色型存取控制](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control) <br/> |
|驗證您的回應群組部署  <br/> |測試接聽群組搜尋和互動語音回應工作流程的來電，以確保您的設定如預期般運作。  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>工作流程建立案例概述

當您建立工作流程時，有兩種可能的情況：

- **系統管理員建立及設定工作流程** - CsResponseGroupAdministrator 角色成員 (或同等權限) 建立及啟動工作流程和工作流程中的所有元素，例如代理群組、佇列、假日和上班時間、等候音樂等。

- **系統管理員建立工作流程，而一般管理員設定選項** - CsResponseGroupAdministrator 角色成員 (或同等權限) 定義主要 SIP URI、顯示名稱，指派一或多個 CsResponseGroupManager 角色成員，以及選取佇列並啟動工作流程。然後，CsResponseGroupManager 會登入並編輯工作流程設定，包括建立代理群組、將群組指派給佇列，以及設定電話號碼、假日和上班時間、等候音樂等。

    > [!NOTE]
    > 當您想建立受管理的工作流程時，您必須建立並啟動工作流程。儲存作用中的受管理工作流程之後，即可修改及停用工作流程。