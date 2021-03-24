---
title: 設定商務用 Skype Server 中的電話撥入式會議
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: 摘要：閱讀此主題以瞭解如何在商務用 Skype Server 中設定電話撥入式會議。
ms.openlocfilehash: 5f618e22cc45585baddf1e8d6090b9e211dc5681
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103849"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a>設定商務用 Skype Server 中的電話撥入式會議
 
**摘要：** 閱讀此主題以瞭解如何在商務用 Skype Server 中設定電話撥入式會議。
  
在您建立包含會議工作負載的拓撲，以及所選的電話撥入式會議之後，您必須執行額外的步驟來設定電話撥入式會議。 在閱讀本主題之前，請確定您已在商務用 skype server 中的 [電話撥入式會議](../../plan-your-deployment/conferencing/dial-in-conferencing.md)、 [硬體和軟體需求](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)，以及 [電話撥入式會議的部署流程圖及檢查清單](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing)中，進行了閱讀計畫。 
  
若要設定電話撥入式會議，您必須執行下列工作：
  
- [設定撥號對應表](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [設定電話撥入式會議區域](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [設定撥入存取號碼](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [設定會議原則](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [將行 URI 指派給使用者帳戶](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
此外，您也可以執行下列選擇性工作。 如需這些選用任務的詳細資訊，請參閱 [在商務用 Skype Server 中管理電話撥入式會議](../../manage/conferencing/dial-in-conferencing.md)。
  
- 管理電話撥入式會議的 PIN 原則
    
- 管理 DTMF 命令的按鍵對應
    
- 建立會議目錄
    
- 管理會議加入和離開宣告
    
- 測試電話撥入式會議設定
    
- 傳送歡迎使用郵件給撥入使用者
    
## <a name="configure-dial-plans"></a>設定撥號對應表
<a name="BKMK_ConfigureDialPlans"> </a>

當您部署電話撥入式會議時，您必須建立或修改一或多個用於路由撥入存取電話號碼的撥號對應表。 您也必須確定每個撥號對應表至少包含一個正規化規則，此規則會將電話分機分機以 e.164 格式轉換成完整的電話號碼。 
  
使用電話撥入式會議加入會議的使用者，將其個人身分識別號碼 (PIN) 和其電話號碼輸入，以供已驗證的企業使用者加入會議。 您需要正規化規則，將分機轉換成完整的電話號碼，讓使用者在輸入電話分機時可驗證。
  
若要設定電話撥入式會議的撥號對應表：
  
- 不論您是部署企業語音，請修改全域撥號對應表，以加入電話撥入式會議區域，並確定正規化規則正確地轉換您的撥入存取號碼。 如需詳細指示，請參閱 [在商務用 Skype Server 中建立或修改撥號對應](../../deploy/deploy-enterprise-voice/dial-plans.md)表。
    
- 如果您未部署企業語音，請建立電話撥入式會議存取號碼的撥號對應表。 請務必加入電話撥入式會議區域。 如需詳細指示，請參閱 [在商務用 Skype Server 中建立或修改撥號對應](../../deploy/deploy-enterprise-voice/dial-plans.md)表。
    
- 如果您部署了企業語音，請視需要修改 Enterprise Voice 撥號對應表，以包含地區，並使用適當的正規化規則來撥打撥入存取號碼。 您也可以建立專用的撥號對應表，只用于撥入存取號碼。 如需詳細指示，請參閱 [在商務用 Skype Server 中建立或修改撥號對應](../../deploy/deploy-enterprise-voice/dial-plans.md)表。
    
如需建立正規化規則的詳細資訊，請參閱 [在商務用 Skype 中建立或修改正規化規則](../../deploy/deploy-enterprise-voice/normalization-rules.md)。
  
## <a name="configure-dial-in-conferencing-regions"></a>設定電話撥入式會議區域
<a name="BKMK_ConfigureDialInRegions"> </a>

設定撥號對應表時，您會指定適用於該撥號對應表的電話撥入式會議區域。 電話撥入式會議區域會將電話撥入式會議存取號碼與適當的撥號對應表產生關聯。 當您建立撥入存取號碼時，請選取相關聯的撥號對應表的存取號碼相關聯的地區。 
  
由於為所有的撥號對應表指定區域很重要，因此建議您確認所有的撥號對應表都有會議地區。 
  
若要確認是否已設定所有電話撥入式會議撥號對應表的區域，請使用 **Get-CsDialPlan** Cmdlet。 如果撥號對應表缺少區域，您可以使用 **Set-CsDialPlan** Cmdlet 來設定區域。 您也可以使用商務用 Skype Server 控制台更新現有撥號對應表中的區域。 如需使用商務用 Skype Server 控制台的詳細資訊，請參閱 [在商務用 Skype server 中建立或修改撥號對應](../../deploy/deploy-enterprise-voice/dial-plans.md)表。
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>若要確認撥號對應表是否已設定區域屬性

1. 以 RTCUniversalServerAdmins 群組成員或 **Cs-VoiceAdministrator**、**Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。
    
3. 在命令提示字元中執行下列命令：
    
   ```powershell
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   例如：
    
   ```powershell
   Get-CsDialPlan
   ```

   在此範例中，會傳回組織中所有已設定的撥號對應表。
    
4. 檢閱傳回的撥號對應表，檢查是否有任何一項缺少電話撥入式會議區域。 
    
如需詳細資訊，請參閱 [Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps)。
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a>若要設定撥號對應表的區域屬性

1. 以 RTCUniversalServerAdmins 群組成員或 **Cs-VoiceAdministrator**、**Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。
    
3. 針對任何缺少電話撥入式會議區域的撥號對應表，執行：
    
   ```powershell
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   例如：
    
   ```powershell
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   在此範例中，將修改識別為 Redmond 的撥號對應表，以將其 DialinConferencingRegion 屬性設為 "US West Coast"。 
    
如需詳細資訊，請參閱 [Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps)。
  
## <a name="configure-dial-in-access-numbers"></a>設定撥入存取號碼
<a name="BKMK_ConfigureDialInAccessNumbers"> </a>

當您部署電話撥入式會議時，您必須設定使用者可以從公用交換電話網路 (PSTN) 撥打的電話號碼，以加入會議的音訊部分。 這些撥入存取號碼會顯示在會議邀請和電話撥入式會議設定網頁上。
  
在您可以建立撥入存取號碼之前，您必須先規劃撥入式會議區域，然後使用地區設定撥號對應表。 如需地區的詳細資訊，請參閱 [在商務用 Skype Server 中規劃撥入式會議](../../plan-your-deployment/conferencing/dial-in-conferencing.md)。 如需設定電話撥入式會議的撥號對應表的詳細資訊，請參閱 [在商務用 Skype Server 中建立或修改撥號對應](../../deploy/deploy-enterprise-voice/dial-plans.md)表。
  
> [!NOTE]
> 您無法使用新的撥入存取號碼，除非 Active Directory 網域服務 (AD DS) 該存取號碼的複寫已完成。 複寫可能需要數小時才能完成。 
  
> [!NOTE]
> 在您建立撥入存取號碼之後，您可以修改 Active Directory 連絡人物件的顯示名稱，讓使用者可以更輕鬆地識別正確的存取號碼。 若要修改顯示名稱，請使用 [Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) Cmdlet。 您不應該手動修改 Active Directory 物件。
  
### <a name="to-create-a-dial-in-access-number"></a>若要建立撥入存取號碼

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 開啟商務用 Skype Server 控制台。
    
3. 在左導覽列中，按一下 **[會議]**，然後按一下 **[撥入存取號碼]**。
    
4. 在 **[撥入存取號碼]** 頁面中，執行下列其中一項：
    
   - 按一下 **[新增]** 以開啟 **[新增撥入存取號碼]**。
    
   - 按一下清單中的其中一個撥入存取號碼，按一下 **[編輯]**，然後按一下 **[顯示詳細資料]**。
    
     > [!NOTE]
     > 使用搜尋欄位來搜尋撥入存取號碼清單中可能無法產生預期結果的欄內容。請依照您想要的欄排序此清單，找出您想檢視或變更的撥入存取號碼。 
  
5. 在 [ **顯示號碼**] 中，輸入公用交換電話網路 (PSTN) 電話使用者撥號以加入會議的電話號碼。 此號碼會顯示在會議邀請中和電話撥入式會議設定網頁上。
    
6. 在 [ **顯示名稱**] 中，輸入撥入存取號碼的描述。 這是商務用 Skype 搜尋結果中與撥入存取號碼相關聯的名稱。 當使用者呼叫存取號碼時，此名稱會顯示在用戶端中。 
    
7. 在 [ **行 uri**] 中，輸入電話 uri 格式的撥入存取號碼的 e.164 號碼，包含號碼前面的 + 符號，並排除空格。 例如電話： + 14255550200。
    
    > [!NOTE]
    > 其他電話撥入式會議存取號碼無法重複使用相同的列 URI。 
  
8. 在 [ **SIP URI**] 中，執行下列動作：
    
   - 在文字方塊中，輸入此撥入式會議存取號碼的唯一 SIP URI。 這種 SIP URI 會顯示在不同的位置，包括（但不限於）來電通知訊息和舊版的 Lync 用戶端。
    
     > [!NOTE]
     > 其他電話撥入式會議存取號碼無法重複使用相同的 SIP URI。 建立存取號碼之後，便無法修改 SIP URI。 變更 SIP URI 的唯一方法是刪除並重新建立存取號碼。 
  
   - 在下拉式清單方塊中，按一下支援此撥入存取號碼之會議應答應用程式的網域。
    
9. 在 [ **集** 區] 中，按一下執行支援此撥入存取號碼之會議助理實例的集區。
    
    > [!NOTE]
    > 如果您在建立存取號碼之後需要變更集區，則必須使用 [Move-CsApplicationEndpoint](/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) Cmdlet，或刪除並重新建立存取號碼。
  
10. 在 [ **主要語言**] 中，按一下為此撥入存取號碼播放提示時所使用的語言。 
    
    主要語言是會議助理用來接聽通話的語言。 在 [電話撥入式會議設定] 網頁上的每一個存取電話號碼旁會顯示支援的語言。
    
11.  (選用) 在 **次要語言中 (最多四個)**，請按一下 [ **新增**]，選取您要支援的來電者撥打此撥入存取號碼的一或多個其他語言，然後按一下 **[確定]**。 
    
    您最多可以為每個撥入存取號碼選擇四種次要語言。 使用者在撥入會議時，可以先選取次要語言，再進入會議識別碼。
    
12. 若要新增撥入存取號碼的地區，請在 [ **關聯的地區**] 下，按一下 [ **新增**]，然後按一下與此撥入存取號碼的撥號對應表相關聯的一個或多個地區，然後按一下 **[確定]**。
    
13. 若要從撥入存取號碼中刪除地區，請在 [ **關聯的地區**] 下，按一下您要刪除的地區，然後按一下 [ **移除**]。
    
14. 按一下 **[認可]**。
    
## <a name="configure-conferencing-policies"></a>設定會議原則
<a name="BKMK_ConfigureConferencingPolicies"> </a>

會議原則是一種使用者帳戶設定，可指定參與者的會議體驗。 您可以建立具有網站範圍或使用者範圍的會議原則。 會議原則設定涵蓋許多會議排程和參與的層面。 數個會議原則設定支援參與者的電話撥入式會議。 當您設定電話撥入式會議時，應確認您的組織已正確設定這些欄位，並視需要加以修改。 
  
如需設定會議原則的詳細資訊，請參閱 [在商務用 Skype Server 中管理會議原則](../../manage/conferencing/conferencing-policies.md)。
  
## <a name="assign-a-line-uri-to-a-user-account"></a>將行 URI 指派給使用者帳戶
<a name="BKMK_AssignaLineURI"> </a>

撥入使用者輸入他們的電話號碼或分機號碼，以及將會議加入已驗證使用者的 PIN 碼。 驗證需要在商務用 Skype Server 使用者帳戶上指定的電話語音 **行 URI** 。
  
本主題中的程式說明如何為單一使用者帳戶指派 **行 URI** 。 如果您需要為多個使用者帳戶指派 **行 URI** ，您可以建立使用 **Set-CsUser** Cmdlet 的腳本。 如需使用範例腳本將 **行 URI** 指派給多個使用者帳戶的詳細資訊，請參閱 [指派行 URIs 給多位使用者](https://go.microsoft.com/fwlink/p/?linkId=196945)。
  
1. 以 RTCUniversalServerAdmins 群組成員的身分，或是 **Cs-UserAdministrator** 或 **CsAdministrator** 角色的成員身分登入電腦。
    
2.  開啟商務用 Skype Server 控制台。
    
3. 在左導覽列中，按一下 **[使用者]**。
    
4. 在 [搜尋] 欄位中，輸入您要設定電話撥入式會議的使用者名稱，或按一下 [ **新增篩選** ] 以指定搜尋欄位，然後按一下 [ **尋找**]。
    
5. 連按兩下使用者名稱，以開啟 [ **編輯商務用 Skype Server 使用者** ] 對話方塊。
    
6. 在 [ **電話語音**] 下的 [ **線路 URI** ] 欄位中，輸入唯一且正規化的電話號碼 (例如電話： + 14255550200) 。
    
    > [!NOTE]
    > 只有在 **電話語音** 設定為 **僅限 pc 對電腦**、 **Enterprise Voice**、**遠端呼叫控制** 或 **遠端呼叫控制** 時，您才可以指定 **行 URI** 。 
  
7. 按一下 **[認可]**。
