---
title: 商務用 Skype 中的回應群組部署程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: 商務用 Skype Server Enterprise Voice 中的 [部署程式] 和 [回應] 群組步驟。
ms.openlocfilehash: 12497d143f9ff5c7630f81db8f416e2f7c74d574
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233524"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>商務用 Skype 中的回應群組部署程式

商務用 Skype Server Enterprise Voice 中的 [部署程式] 和 [回應] 群組步驟。

[回應] 群組是一個企業語音功能, 可將來電路由並列隊給一組人員 (例如服務台或客戶服務台)。

當您部署企業語音時, 會在前端伺服器或標準版伺服器上自動安裝及啟用回應群組所需的元件。 若要讓使用者使用 [回應群組], 您必須先設定 [代理群組]、[佇列], 然後再設定 [工作流程]。 此外, 回應群組管理員可以將現有工作流程的設定委派給回應群組管理員, 然後可以修改及重新設定工作流程及其關聯的代理群組和佇列。

若要設定回應群組, 您必須是下列至少一個管理角色的成員:

|**Active Directory 安全性群組 (1)** <br/> |建立工作流程  <br/> |指派管理員  <br/> |建立/assign 代理程式、佇列  <br/> |建立/管理假日與上班時間  <br/> |啟動/停用工作流程  <br/> |設定工作流程 (IVR 或查尋群組)  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**CsResponseGroupAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsResponseGroupManager** <br/> ||√ (2)  <br/> |√ (3)  <br/> |√ (3)  <br/> |√ (3)  <br/> |√ (3)  <br/> |
|**CsVoiceAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsServerAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsViewOnlyAdministrator** <br/> |√ (4)  <br/> |√ (4)  <br/> |√ (4)  <br/> |√ (4)  <br/> |√ (4)  <br/> |√ (4)  <br/> |

> [!NOTE]
> **(1)** Active Directory 網域服務使用者物件必須是所列指定 Active directory 安全性群組的成員。 具有適當許可權的系統管理員或其他受委派 Active Directory 群組成員 (例如, 管理員、帳戶操作員) 必須將使用者物件新增至所列的安全群組或群組, 使用者才能執行所列的函數。 **(2)** 僅適用于 CsResponseGroupAdministrator 已指派給 CsResponseGroupManager 的工作流程。 **(3)** 回應群組管理員可以將 CsResponseGroupManager 的另一個成員指派給目前管理員已管理的工作流程。 **(4)** CsViewOnlyAdministrator 只能執行動詞 "取得" Cmdlet。

## <a name="response-group-configuration-prerequisites"></a>回應群組設定的先決條件

回應群組需要下列元件:

- 應用程式服務

- 回應群組應用程式

- 語言套件

- 檔案存放區 (儲存音訊檔案)

- Web 服務 (包括回應群組設定工具以及代理程式的登入和登出主機)

當您部署企業語音時, 系統會預設安裝這些元件。

在設定回應群組之前, 您可能需要執行下列工作:

- 允許使用者使用 Lync Server 2013 和企業版語音。

- 修改要與聯邦資訊處理標準 (FIPS) 相容的設定檔。

- 修改資料庫排序規則, 以支援佇列名稱和代理群組名稱的 Yi、Meng 及 Zang 字元。

### <a name="enabling-users"></a>啟用使用者

配置回應群組的第一個步驟是建立代理群組。 在您可以建立代理群組之前, 您必須先啟用將擁有商務用 Skype 和企業語音之回應群組的使用者。 啟用商務用 Skype 的使用者通常是企業版 server 或標準版伺服器部署中的一個步驟。 如需有關針對商務用 Skype 啟用使用者的詳細資訊, 請參閱[啟用或停用 Lync Server 2013 Preview 的使用者](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)。 啟用企業語音的使用者通常是企業語音部署中的一個步驟。 如需詳細資訊, 請參閱[在商務用 Skype 伺服器中啟用企業語音的使用者](enable-users-for-enterprise-voice.md)。

### <a name="complying-with-fips-requirements"></a>遵守 FIPS 需求

本節僅適用于您的組織必須遵循聯邦資訊處理標準 (FIPS) 的情況。

若要符合 FIPS, 您必須在安裝 Web 服務之後, 修改應用程式層級的 web.config 檔案, 以使用不同的密碼演算法。 您必須指定 ASP.NET 使用 [三重資料加密標準 (3DES)] 演算法來處理檢視狀態資料。 針對回應群組應用程式, 此需求會套用至回應群組設定工具以及代理程式登入和登出主機。 如需此需求的詳細資料, 請參閱 Microsoft 知識庫文章 911722: 當您在從 ASP.NET 1.1 升級至 ASP.NET 2.0 之後, 當您存取已啟用 ViewState 的 ASP.NET 網頁時, 您可能會[https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183)收到錯誤訊息。

若要修改 web.config 檔案, 請執行下列動作:

1. 在記事本等文字編輯器中, 開啟應用程式層級的 web.config 檔案。

2. 在 web.config 檔案中, 找到該`<system.web>`節。

3. 在`<system.web>`區段中`<machineKey>`新增下列區段:

   ```
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. 儲存 web.config 檔案。

5. 在命令提示字元執行下列命令, 以重新開機網際網路資訊服務 (IIS) 服務:

   ```
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>支援 Yi、Meng 和 Zang 字元

本節僅適用于您的組織必須支援 Yi、Meng 或 Zang 字元的情況。

> [!NOTE]
> 如需彝語、Meng 和 Zang 字元的用途, 以及它們對於您的部署而言可能很重要的原因, 請參閱 GB18030 字元集合[https://go.microsoft.com/fwlink/p/?linkId=240223](https://go.microsoft.com/fwlink/p/?linkId=240223)上的資訊。

若要支援 Yi、Meng 或 Zang 字元, 您必須修改 Rgsconfig 資料庫的排序規則。 在每個 Rgsconfig 資料庫的下清單格中, 變更 [**名稱**] 資料行的排序規則:

- 擁有者.AgentGroups

- 擁有者.BusinessHours

- 擁有者.HolidaySets

- 擁有者.佇列

- 擁有者.工作流程

針對 SQL Server 2008 R2 與 SQL Server 2012, 請使用 Latin_General_100 (輔色) 排序規則。 如果您使用此排序規則, 則所有物件名稱都不區分大小寫。

您可以使用 Microsoft SQL Server Management Studio 變更排序規則。 如需使用此工具的詳細資訊, 請參閱「[使用 SQL Server Management Studio](https://go.microsoft.com/fwlink/p/?linkId=196184)」。 請依照下列步驟變更排序規則:

1. 確定 SQL Server Management Studio 已設定為允許重新建立需要資料表的變更。 如需詳細資訊, 請參閱「[儲存 (不允許) 對話方塊](https://go.microsoft.com/fwlink/p/?linkId=196186)」。 如需設定欄排序規則的詳細資料, 請參閱「[如何: 設定欄排序規則 (視覺化資料庫工具)](https://go.microsoft.com/fwlink/p/?linkId=196185)」。

2. 使用 Microsoft SQL Server Management Studio 連接到 Rgsconfig 資料庫。

3. 在 Rgsconfig 資料庫中尋找您要變更的資料表, 以滑鼠右鍵按一下資料表, 然後按一下 [**設計**]。

4. 變更 [**名稱**] 資料行的排序規則, 並儲存資料表。

## <a name="response-group-deployment-steps"></a>回應群組部署步驟

**回應群組部署程式**

|**分**|**步驟**|**許可權**|**部署檔**|
|:-----|:-----|:-----|:-----|
|允許使用者使用商務用 Skype 和企業語音  <br/> |啟用將是商務用 Skype 和企業語音的使用者。 您必須先啟用使用者, 才能將其新增至代理群組。 通常, 在企業版或標準版伺服器部署期間, 會啟用商務用 Skype 的使用者。 在企業語音部署期間, 系統會為使用者啟用企業語音。  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[啟用或停用 Lync Server 2013 Preview 的使用者](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx) <br/> [在商務用 Skype Server 中啟用企業語音的使用者](enable-users-for-enterprise-voice.md) <br/> |
|建立及設定回應群組, 包括代理群組、佇列和工作流程  <br/> |1. 使用商務用 Skype Server 的 [控制台] 或 [商務用 Skype 伺服器管理命令介面] 執行下列動作:  <br/> 是. 建立及設定代理群組。  <br/> 乙. 建立及設定佇列。  <br/> 2. 您也可以使用商務用 Skype Server Management Shell 來建立預先定義的回應群組商務時數和假日。  <br/> 3. 使用 [回應群組設定] 工具或 [商務用 Skype 伺服器管理命令介面] 來建立工作流程 (查尋群組或互動式語音回應 (IVR) 通話流程), 包括自訂回應群組的商務時間和假日。  <br/> 您可以透過商務用 Skype Server 的 [控制台] 存取回應群組設定工具。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[建立回應群組代理群組](https://technet.microsoft.com/library/2a80de17-ead0-46e8-8a27-7a4e233dbde0.aspx) <br/> [建立回應群組佇列](https://technet.microsoft.com/library/49cb86c7-2cfd-4a53-8408-d407475174ed.aspx) <br/> [可選在商務用 Skype 中定義回應群組上班時間](optional-define-response-group-business-hours.md) <br/> [可選在商務用 Skype 中定義回應群組假日集](optional-define-response-group-holiday-sets.md) <br/> [在商務用 Skype 中設計及建立回應群組工作流程](designing-and-creating-response-group-workflows.md) <br/> |
|可選自訂應用程式層級設定  <br/> |使用商務用 Skype Server Management 命令介面來自訂預設的音樂保留式設定、預設的音樂保留音訊檔案、代理 ringback 寬限期, 以及通話內容設定。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[管理商務用 Skype 中的應用層級回應群組設定](managing-application-level-response-group-settings.md) <br/> |
|可選委派對回應群組的管理  <br/> |指派使用者的 CsResponseGroupManager 角色來委派回應群組的設定。 回應群組管理員可以設定指派給他們的回應群組。  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[規劃以角色為基礎的存取控制](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) <br/> |
|驗證您的回應群組部署  <br/> |測試對您的查尋群組和互動式語音回應工作流程的通話回應, 以確保您的設定如預期的那樣正常運作。  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>建立工作流程的案例概觀

當您建立工作流程時, 有兩種可能的案例:

- **系統管理員建立並設定工作流程**— CsResponseGroupAdministrator 角色成員 (或對等) 會建立並啟用工作流程及工作流程中的所有元素, 例如代理群組、佇列、假日和上班時間。[等候音樂] 等等。

- **系統管理員會建立工作流程, 且**管理員會設定選項, 例如, CsResponseGroupAdministrator 角色成員 (或對等) 會定義主要 SIP URI、顯示名稱、指派 CsResponseGroupManager 角色的成員或成員, 以及選取佇列並啟用工作流程。 CsResponseGroupManager 可接著建立代理群組, 並將該群組指派給該佇列, 然後將該群組指派給該隊, 然後設定電話號碼、假日與上班時間、暫停音樂等。

    > [!NOTE]
    > 當您想要建立受管理的工作流程時, 您必須建立作用中的工作流程。 儲存使用中的受管理工作流程之後, 您就可以修改及停用工作流程。


