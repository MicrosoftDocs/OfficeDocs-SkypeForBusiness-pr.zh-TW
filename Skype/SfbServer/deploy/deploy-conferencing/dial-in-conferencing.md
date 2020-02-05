---
title: 在商務用 Skype Server 中設定電話撥入式會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: 摘要：請閱讀本主題，以瞭解如何在商務用 Skype Server 中設定電話撥入式會議。
ms.openlocfilehash: 4e8523cbaadfc13b985cf33e06e68fcd5d209c89
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768526"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a>在商務用 Skype Server 中設定電話撥入式會議
 
**摘要：** 若要瞭解如何在商務用 Skype Server 中設定電話撥入式會議，請閱讀本主題。
  
在您建立包含會議工作負荷與已選取電話撥入式會議的拓撲之後，您必須執行其他步驟來設定電話撥入式會議。 在您閱讀本主題之前，請確定您已閱讀商務用 Skype server 的[電話撥入式會議](../../plan-your-deployment/conferencing/dial-in-conferencing.md)、[商務用 skype server 的硬體及軟體需求](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)，以及[電話撥入式會議的部署流程圖與檢查清單](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing)。 
  
若要設定電話撥入式會議，您必須執行下列工作：
  
- [設定撥號方案](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [設定電話撥入式會議區域](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [設定撥入存取號碼](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [設定會議原則](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [將行 URI 指派給使用者帳戶](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
此外，您也可以執行下列選用的工作。 如需這些選用工作的詳細資訊，請參閱[管理商務用 Skype Server 中的電話撥入式會議](../../manage/conferencing/dial-in-conferencing.md)。
  
- 管理電話撥入式會議的 PIN 原則
    
- 管理 DTMF 命令的金鑰組應
    
- 建立會議目錄
    
- 管理會議加入與離開宣告
    
- 測試電話撥入式會議設定
    
- 傳送歡迎郵件給撥入使用者
    
## <a name="configure-dial-plans"></a>設定撥號方案
<a name="BKMK_ConfigureDialPlans"> </a>

當您部署電話撥入式會議時，您需要建立或修改路由撥入存取電話號碼的一個或多個撥號方案。 您也必須確認每個撥號方案都至少包含一個標準化規則，這項規則會將電話分機轉換成以164格式的完整電話號碼。 
  
電話撥入式會議以已驗證的企業使用者身分加入會議的使用者，只要輸入其個人識別碼（PIN）及他們的電話號碼即可。 您需要正常化規則，將延伸轉換成完整的電話號碼，讓使用者在輸入電話分機時就能進行驗證。
  
若要為電話撥入式會議設定撥號方案，請執行下列動作：
  
- 不論是否要部署企業語音，請修改全域撥號方案以新增電話撥入式會議區域，並確認正常化規則正確地轉換您的撥入存取號碼。 如需詳細指示，請參閱[在商務用 Skype Server 中建立或修改撥號方案](../../deploy/deploy-enterprise-voice/dial-plans.md)。
    
- 如果您沒有部署企業語音，請為電話撥入式會議存取號碼建立撥號方案。 請務必包含電話撥入式會議區域。 如需詳細指示，請參閱[在商務用 Skype Server 中建立或修改撥號方案](../../deploy/deploy-enterprise-voice/dial-plans.md)。
    
- 如果您已部署企業語音，請根據需要修改企業語音撥號方案，以加入地區，並針對撥入存取號碼使用適當的正常化規則。 您也可以建立只用于撥入存取號碼的專用撥號方案。 如需詳細指示，請參閱[在商務用 Skype Server 中建立或修改撥號方案](../../deploy/deploy-enterprise-voice/dial-plans.md)。
    
如需建立正常化規則的詳細資料，請參閱[在商務用 Skype 中建立或修改正常化規則](../../deploy/deploy-enterprise-voice/normalization-rules.md)。
  
## <a name="configure-dial-in-conferencing-regions"></a>設定電話撥入式會議區域
<a name="BKMK_ConfigureDialInRegions"> </a>

當您設定撥號方案時，請指定適用于該撥號方案的電話撥入式會議區域。 電話撥入式會議區域會將電話撥入式會議存取號碼與適當的撥號方案進行關聯。 當您建立撥入存取號碼時，請選取將存取號碼與適當的撥號方案相關聯的地區。 
  
因為為所有撥號方案指定區域很重要，所以建議您確認所有撥號方案都有會議區域。 
  
若要驗證是否已針對所有電話撥入式會議撥號方案設定區域，請使用**CsDialPlan** Cmdlet。 如果撥號方案中的區域遺失，您可以使用**CsDialPlan** Cmdlet 來設定區域。 您也可以使用商務用 Skype Server 的 [控制台] 來更新現有撥號方案中的區域。 如需使用商務用 Skype Server [控制台] 的詳細資料，請參閱[在商務用 Skype server 中建立或修改撥號方案](../../deploy/deploy-enterprise-voice/dial-plans.md)。
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>驗證撥號方案是否已設定 region 屬性

1. 以 RTCUniversalServerAdmins 群組的成員或**cs-VoiceAdministrator**、 **cs-ServerAdministrator**或**CsAdministrator**角色的成員的身分登入電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。
    
3. 在命令提示字元執行下列動作：
    
   ```powershell
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   例如：
    
   ```powershell
   Get-CsDialPlan
   ```

   在這個範例中，會傳回為貴組織設定的所有撥號計畫。
    
4. 查看傳回的撥號方案，以找出遺失電話撥入式會議區域的任何專案。 
    
如需詳細資訊，請參閱[CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps)。
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a>若要設定撥號方案的 region 屬性

1. 以 RTCUniversalServerAdmins 群組的成員或**cs-VoiceAdministrator**、 **cs-ServerAdministrator**或**CsAdministrator**角色的成員的身分登入電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。
    
3. 針對遺失電話撥入式會議區域的任何撥號方案，請執行：
    
   ```powershell
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   例如：
    
   ```powershell
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   在這個範例中，會修改具有雷德蒙者身分識別的撥號計畫，以將 DialinConferencingRegion 屬性設為 "US West Coast"。 
    
如需詳細資訊，請參閱[設定 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps)。
  
## <a name="configure-dial-in-access-numbers"></a>設定撥入存取號碼
<a name="BKMK_ConfigureDialInAccessNumbers"> </a>

當您部署電話撥入式會議時，您必須設定使用者可從公用交換電話網絡（PSTN）撥打電話的電話號碼，以加入會議的音訊部分。 這些撥入存取號碼會出現在會議邀請和 [電話撥入式會議設定] 網頁上。
  
您必須先規劃撥入式會議區域，然後設定與地區的撥號方案，才能建立撥入號碼。 如需地區的詳細資料，請參閱[在商務用 Skype 伺服器中規劃電話撥入式會議](../../plan-your-deployment/conferencing/dial-in-conferencing.md)。 如需有關設定電話撥入式會議的撥號方案的詳細資訊，請參閱[在商務用 Skype Server 中建立或修改撥號方案](../../deploy/deploy-enterprise-voice/dial-plans.md)。
  
> [!NOTE]
> 在該存取號碼的 Active Directory 網域服務（AD DS）複製完成之前，您無法使用新的撥入存取號碼。 複製可能需要幾個小時才能完成。 
  
> [!NOTE]
> 在您建立撥入存取號碼之後，您可以修改 Active Directory 連絡人物件的顯示名稱，讓使用者能更輕鬆地識別正確的存取號碼。 若要修改顯示名稱，請使用[CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) Cmdlet。 您不應該手動修改 Active Directory 物件。
  
### <a name="to-create-a-dial-in-access-number"></a>建立撥入存取號碼

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2. 開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中，按一下 [**會議**]，然後按一下 [**撥入存取號碼**]。
    
4. 在 [**撥入存取號碼**] 頁面上，執行下列其中一項操作：
    
   - 按一下 [**新增**] 以開啟**新的撥入存取號碼**。
    
   - 按一下清單中的其中一個撥入存取號碼，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。
    
     > [!NOTE]
     > 使用 [搜尋] 欄位來搜尋撥入存取號碼清單中的欄內容，可能不會產生您預期的結果。 您可以改為依您想要查看或變更的撥入存取號碼來排序清單。 
  
5. 在 [**顯示號碼**] 中，輸入「公用交換電話網絡（PSTN）電話撥打電話給」加入會議的電話號碼。 這個數位會顯示在 [會議邀請] 和 [電話撥入式會議設定] 網頁上。
    
6. 在 [**顯示名稱**] 中，輸入撥入存取號碼的描述。 這是與商務用 Skype 搜尋結果中的撥入存取號碼相關聯的名稱。 當使用者呼叫存取號碼時，此名稱就會顯示在用戶端中。 
    
7. 在 [**行 uri**] 中，輸入電話 uri 格式的撥入存取號碼的 E. 164 個數字，包括數位前面的 + 符號，不含空格。 例如，電話： + 14255550200。
    
    > [!NOTE]
    > 其他電話撥入式會議存取號碼無法重複使用相同的行 URI。 
  
8. 在**SIP URI**中，請執行下列動作：
    
   - 在文字方塊中，輸入此電話撥入式會議存取號碼的唯一 SIP URI。 此 SIP URI 會顯示在不同的位置，包括但不限於呼叫通知訊息及舊版 Lync 用戶端版本。
    
     > [!NOTE]
     > 其他電話撥入式會議存取號碼無法重複使用相同的 SIP URI。 在建立存取號碼之後，便無法修改 SIP URI。 變更 SIP URI 的唯一方式是刪除並重新建立存取號碼。 
  
   - 在下拉式清單方塊中，按一下支援此撥入存取號碼之會議助理應用程式的網域。
    
9. 在 [Pool] （**池**）中，按一下執行支援此撥入存取號碼之會議助理實例的池。
    
    > [!NOTE]
    > 如果您在建立存取號碼後需要變更池，您必須使用[CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) Cmdlet，或刪除並重新建立存取號碼。
  
10. 在**主要語言**中，按一下針對此撥入存取號碼播放提示的語言。 
    
    主要語言是會議助理用來接聽通話的語言。 支援的語言會顯示在電話撥入式會議設定網頁上的每個存取電話號碼旁邊。
    
11. 可選在**次要語言（最多四個）** 中，按一下 [**新增**]，選取您想要支援來電者至此撥入存取號碼的一或多個其他語言，然後按一下 **[確定]**。 
    
    您最多可以為每個撥入存取號碼選擇四個次要語言。 使用者在撥入會議時，輸入會議 ID 前，就可以選取次要語言。
    
12. 若要新增撥入存取號碼的地區，請在 [**相關區域**] 底下，按一下 [**新增**]，按一下與此撥入存取號碼的撥號方案相關聯的一個或多個區域，然後按一下 **[確定]**。
    
13. 若要從撥入存取號碼刪除區域，請在 [**相關區域**] 底下，按一下您要刪除的區域，然後按一下 [**移除**]。
    
14. 按一下 [認可]****。
    
## <a name="configure-conferencing-policies"></a>設定會議原則
<a name="BKMK_ConfigureConferencingPolicies"> </a>

[會議原則] 是一個使用者帳戶設定，可為參與者指定會議體驗。 您可以使用網站範圍或使用者範圍建立會議原則。 會議原則設定涵蓋了會議排程與參與的許多方面。 幾個會議原則設定支援參與者的電話撥入式會議。 當您設定電話撥入式會議時，應確認這些欄位已針對您的組織進行適當的設定，並視需要加以修改。 
  
如需有關設定會議原則的詳細資訊，請參閱[在商務用 Skype Server 中管理會議原則](../../manage/conferencing/conferencing-policies.md)。
  
## <a name="assign-a-line-uri-to-a-user-account"></a>將行 URI 指派給使用者帳戶
<a name="BKMK_AssignaLineURI"> </a>

[撥入使用者] 輸入他們的電話號碼或分機，以及將會議加入為經過驗證的使用者的 PIN。 在商務用 Skype Server 使用者帳戶上指定的電話**線路 URI**是驗證所必需的。
  
本主題中的程式說明如何為單一使用者帳戶指派**行 URI** 。 如果您需要為多個使用者帳戶指派**行 URI** ，您可以建立使用**move-csuser** Cmdlet 的腳本。 如需使用範例腳本將**行 URI**指派給多個使用者帳戶的詳細資料，請參閱[將行 Uri 指派給多個使用者](https://go.microsoft.com/fwlink/p/?linkId=196945)。
  
1. 以 RTCUniversalServerAdmins 群組的成員或**Cs-UserAdministrator**或**CsAdministrator**角色的成員的身分登入電腦。
    
2.  開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中，按一下 [**使用者**]。
    
4. 在 [搜尋] 欄位中，輸入您要為電話撥入式會議設定的使用者名稱，或按一下 [**新增篩選**] 以指定搜尋欄位，然後按一下 [**尋找**]。
    
5. 按兩下使用者名稱以開啟 [**編輯商務用 Skype 伺服器使用者**] 對話方塊。
    
6. 在 [**電話**] 底下的 [**行 URI** ] 欄位中，輸入唯一的、標準化的電話號碼（例如電話： + 14255550200）。
    
    > [!NOTE]
    > 只有將**電話**設定為 [**僅電腦至電腦**]、[**企業語音**]、[**遠端通話控制**] 或 [**遠端通話控制**] 時，才能指定 [**行 URI** ]。 
  
7. 按一下 [認可]****。
    

