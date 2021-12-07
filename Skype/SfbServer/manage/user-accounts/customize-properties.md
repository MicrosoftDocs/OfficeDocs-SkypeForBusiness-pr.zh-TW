---
title: 自訂商務用 Skype Server 的使用者帳戶屬性
ms.reviewer: ''
ms.author: v-mathavale
author: v-mathavale
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: 您可以使用本節中的程式來修改個別的使用者帳戶屬性。
ms.openlocfilehash: f80847b57122539654541a444f427f4031ee6197
ms.sourcegitcommit: 2aae13454178dc2e2cbc8cca967cd181c5f9d044
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/06/2021
ms.locfileid: "61314201"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>自訂商務用 Skype Server 的使用者帳戶屬性
 
您可以使用本節中的程式來修改個別的使用者帳戶屬性。
 
在個別使用者層級上，有兩種基本作業可以進行：
 
- [設定特定使用者帳戶的電話語音選項](#configure-telephony-options-for-a-specific-user-account)

- [將使用者移至另一個集區](#move-users-to-another-pool)
 
## <a name="configure-telephony-options-for-a-specific-user-account"></a>設定特定使用者帳戶的電話語音選項

您可以自訂特定使用者 (的電話語音設定，只要個別使用者已啟用商務用 Skype Server 且組織支援電話語音) 。
 
商務用 Skype Server 使用者電話語音選項包括下列各項：
 
|電話語音選項  |描述  |
|---------|---------|
|**音訊/視訊已停用**|使用者無法撥打音訊和視訊電話。|
|**僅限電腦對電腦** | 使用者只能撥打電腦對電腦音訊或視訊電話。|
|**企業語音** | 使用者可以使用商務用 Skype Server 基礎結構路由傳送所有來電和撥出電話。 使用者也可以進行電腦對電腦呼叫。|
|**遠端呼叫控制**   | 使用者可以使用商務用 Skype Server 來控制桌面電話，也可以進行電腦對電腦的呼叫。|
 
如需設定組織之電話語音的詳細資訊，請參閱部署檔中的在[商務用 Skype Server 中啟用企業語音](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)和[部署企業語音中商務用 Skype Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) 。
 
### <a name="configure-telephony-options-for-specific-users-using-new-control-panel"></a>使用新控制台設定特定使用者的電話語音選項 
 
1. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。
 
2. 使用指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入。
 
3. 在左窗格中，選取 [ **使用者**]。
 
4. 在 **搜尋** 方塊中，輸入顯示名稱的全部或第一個部分，然後按一下 [ **尋找**]。
 
5. 在表格中，按兩下您要修改的使用者帳戶。
 
6. 在出現的窗格中，按一下 [ **指派的原則**] 旁邊的鉛筆圖示。
 
7. 在 **[電話語音]** 中，執行下列動作：
 
    1. 若要停用使用者的音訊和影片通話，請選取下拉式清單中的 [ **Audio/Video 停用** ]。
 
    2. 若要為使用者啟用 pc 對電腦音訊通訊，但未啟用遠端呼叫控制或企業語音，請選取下拉式清單中的 [**僅限電腦對電腦**]。 針對使用者用於電腦對電腦音訊通訊的電話，指定 **[線路 URI]** 值。
 
    3. 若要依照服務原則類別（包括 pc 對電腦音訊通訊）使用商務用 Skype 基礎結構，路由傳送使用者的電話，請選取下拉式清單中的 [**企業語音**]。 在 **[線路 URI]** 中，指定 Enterprise Voice 的電話號碼。 在 **[撥號對應表原則]** 和 **[語音原則]** 中，指定使用者的適當原則。 若要指定將使用者撥打的電話號碼轉換成 e.164 格式的正規化規則，請在 [ **位置原則** ] 下拉式清單中選取適當的位置設定檔。
 
    4. 若要啟用遠端呼叫控制，可讓使用者從商務用 Skype Server 控制其桌面電話線，以進行 pc 對電腦通話和 pc 對電話的呼叫，請選取下拉式清單中的 [**遠端呼叫控制**]。 在 **[線路 URI]** 中，指定遠端呼叫控制的電話號碼。 使用者必須有桌上電話和用於電話路由的專用交換機 (PBX) 連線。

> [!NOTE]
> 無法使用商務用 Skype Server 2015 的 [新增控制台]。

### <a name="configure-telephony-options-for-specific-users-using-legacy-control-panel"></a>使用舊版控制台為特定使用者設定電話語音選項
 
1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
 
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 
 
3. 在左窗格中，選取 [ **使用者**]。
 
4. 在 **[搜尋使用者]** 方塊中，輸入您要的使用者帳戶的完整或開頭部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI)，然後按一下 **[尋找]**。
 
5. 在表格中，選取您要修改的使用者帳戶。
 
6. 在 [編輯] 功能表中，選擇 [修改]。
 
7. 在 **[電話語音]** 中，執行下列動作：
 
    1. 若要停用使用者的音訊和影片通話，請選取 [ **音訊/影片已停用**]。
 
    2. 若要為使用者啟用 pc 對電腦音訊通訊，但未啟用遠端呼叫控制或企業語音，請選取 [**僅限 pc 對電腦**]。 針對使用者用於電腦對電腦音訊通訊的電話，指定 **[線路 URI]** 值。
 
    3. 若要依照服務原則類別（包括 pc 對電腦音訊通訊）使用商務用 Skype 基礎結構來路由傳送使用者的電話，請選取 [**企業語音**]。 在 **[線路 URI]** 中，指定 Enterprise Voice 的電話號碼。 在 **[撥號對應表原則]** 和 **[語音原則]** 中，指定使用者的適當原則。 若要指定將使用者撥打的電話號碼轉譯為 E.164 格式時的正規化規則，請在 **[位置原則]** 中選取適當的位置設定檔。
 
    4. 若要啟用遠端呼叫控制，可讓使用者從商務用 Skype Server 控制其桌面電話線，以進行 pc 對電腦通話和 pc 對電話的呼叫，請選取 [**遠端呼叫控制**]。 在 **[線路 URI]** 中，指定遠端呼叫控制的電話號碼。 使用者必須有桌上電話和用於電話路由的專用交換機 (PBX) 連線。

## <a name="move-users-to-another-pool"></a>將使用者移至另一個集區

您可以使用商務用 Skype Server 控制台將使用者指派至特定的伺服器或集區。
 
> [!TIP]
> 將所有現有使用者從執行 Lync Server 2010 或更早版本的來源集區移至複雜性 active directory 環境中的商務用 Skype Server 目的地集區，可能會導致 Active directory 複寫速度變慢。 若要避免這種情況，您可以使用搜尋篩選器，從執行 Lync Server 2010 或更早版本的集區中移動使用者，也可以使用商務用 Skype Server 管理命令介面，透過 Cmdlet 移動使用者。 此外，篩選功能可與商務用 Skype Server 使用者搭配使用。 
 
### <a name="move-selected-users-to-a-different-server-or-pool-using-new-control-panel"></a>使用 [新增控制台] 將選取的使用者移至其他伺服器或集區

1. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。
 
2. 使用指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入。 
 
3. 在左窗格中，選取 [ **使用者**]。
 
4. 在 **搜尋** 方塊中，輸入顯示名稱的全部或第一個部分，然後按一下 [ **尋找**]。
 
5. 在表格中，按兩下以選取清單中的特定使用者或使用者。 

6. 在出現的窗格中，按一下 [ **註冊區集** 區] 旁邊的鉛筆圖示。
 
7. 在 [ **移動使用者**] 的下拉式清單中，選取您要將使用者移至其中的集區。
 
8.  (選用) 若目的地伺服器或集區無法使用，請選取 [ **強制** ] 核取方塊。
 
    > [!CAUTION]
    > 如果您選取 [ **強制**]，使用者帳戶會移動，但是會刪除任何關聯的使用者資料 (例如，使用者已排程) 的會議）。 如果您未選取它，帳戶和相關聯的資料都會移動。 

> [!NOTE]
> 無法使用商務用 Skype Server 2015 的 [新增控制台]。

### <a name="move-selected-users-to-a-different-server-or-pool-using-legacy-control-panel"></a>使用舊版控制台將選取的使用者移至不同的伺服器或集區

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
 
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 
 
3. 在左窗格中，選取 [ **使用者**]。
 
4. 在 **[搜尋使用者]** 方塊中，輸入您要的使用者帳戶的完整或開頭部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI)，然後按一下 **[尋找]**。 
 
5. 在表格中，選取清單中的特定使用者或使用者。 
 
6. 在 [執行] 功能表上，選取 [將選取的使用者移至集區]。
 
7. 在 [ **移動使用者**] 中，選取要將使用者移至 [ **目的地註冊區集** 區] 的集區。
 
8.  (選用) 若目的地伺服器或集區無法使用，請選取 [ **強制** ] 核取方塊。
 
    > [!CAUTION]
    > 如果您選取 [ **強制**]，使用者帳戶會移動，但是會刪除任何關聯的使用者資料 (例如，使用者已排程) 的會議）。 如果您未選取它，帳戶和相關聯的資料都會移動。 
 
### <a name="move-users-from-one-pool-to-a-different-pool-by-using-a-filter-using-legacy-control-panel"></a>使用舊版控制台，使用篩選將使用者從一個集區移至另一個集區 

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
 
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 
 
3. 在左窗格中，選取 [ **使用者**]。
 
4. 在 [ **使用者搜尋**] 中，選取 [ **搜尋**]，然後按一下 [ **新增篩選**]。
 
5. 在搜尋準則中，選取 [ **註冊集** 區]，選取 [ **等於**]，選取 [目前的 **集區 FQDN**]，然後按一下 [ **尋找**]。
 
6. 在 [ **動作** ] 功能表上，選取 [ **將所有使用者移至集** 區]。
 
    > [!NOTE]
    > 將篩選套用至現有的一組使用者時，選項 [ **將所有使用者移至** 集區] 是在篩選的使用者子集的內容中，而不是 **所有** 可能的使用者。
 
7. 在 [ **移動使用者**] 的 [ **來源註冊集** 區] 中，選取包含您要移動之使用者帳戶的集區。
 
8. 在 [ **目的地登記集** 區] 中，選取要將使用者移至其中的集區。
 
9.  (選用) 若目的地伺服器或集區無法使用，請選取 [ **強制** ] 核取方塊。
 
    > [!CAUTION]
    > 如果您選取 [ **強制**]，使用者帳戶會移動，但是會刪除任何關聯的使用者資料 (例如，使用者已排程的會議，以及) 的連絡人。 如果您未選取它，帳戶和相關聯的資料都會移動。 
 
### <a name="move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 將使用者從一個集區移至另一個集區

1. 根據您執行 Windows PowerShell 命令 (（本機或遠端) ）的方式，您必須以正確商務用 Skype Server 系統管理角色的成員身分登入，如下所示：
 
    1. 如果您是在本機電腦上執行命令 (例如，您可以直接登入前端伺服器) ：以 RTCUniversalServerAdmins 群組成員的身分或必要使用者權限的方式，登入安裝商務用 Skype Server 管理命令介面的電腦（如 **委派安裝許可權** 中所述）。
 
    2. 如果您是在另一部電腦上遠端執行命令 (例如，您登入您的電腦，並從 Standard Edition 前端伺服器遠端執行命令) ：從指派給 CsUserAdministrator 角色的使用者帳戶或 CsAdministrator 角色，登入內部部署中的任何電腦。
 
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
 
3. 若要移動單一使用者，請使用 Move-CsUser Cmdlet，如下所示：
 
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    若要移動的使用者為使用者 Pilar Ackerman，使用者將從目前指派的主集區移至集區 pool01.contoso.net
 
4. 若要移動大量的使用者，請搭配 **Get-CsUser** Cmdlet 使用篩選器，並將產生的使用者集合傳遞給 **Move-CsUser**：
 
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    **Get-CsUser** 和 **Move-CsUser** 的合併命令可能會造成下列情況：
 
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


