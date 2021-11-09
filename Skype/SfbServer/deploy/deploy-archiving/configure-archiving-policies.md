---
title: 設定商務用 Skype Server 的封存原則
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 摘要：閱讀此主題以瞭解如何為商務用 Skype Server 使用者設定初始封存原則。
ms.openlocfilehash: 96d53ae71a8faa72c5dcdc3816c09c1b6d492e67
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853787"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a>設定商務用 Skype Server 的封存原則
 
**摘要：** 閱讀此主題以瞭解如何為商務用 Skype Server 使用者設定初始封存原則。
  
在商務用 Skype Server 中，您可以使用原則為位於商務用 Skype Server 上的使用者啟用和停用內部通訊和外部通訊的封存。 其中包括下列項目：
  
- 當您部署商務用 Skype Server 時預設建立的全域原則
    
- 選用的網站層級原則，指定如何為特定網站實施封存
    
- 選用的使用者層級原則，指定如何為特定使用者執行封存
    
您在部署封存時，最初會設定封存原則，但您可以在部署後變更、新增和刪除原則。 在商務用 Skype Server 控制台中，您可以使用封存 **與監控** 群組的「封存 **原則**」頁面，以管理全域、網站及使用者層級的原則。
  
> [!NOTE]
> 若要控制封存的實施，您必須指定選項，例如是否封存 IM 或會議、使用重要模式，以及清除選項。 根據預設，全域封存設定或任何網站或集區封存設定中未啟用任何選項。 您應該先指定所有適當的選項，才能啟用內部或外部通訊的封存。 如需詳細資訊，請參閱[設定商務用 Skype Server 的封存選項](configure-archiving-options.md)。 
  
> [!NOTE]
> 如果您為部署啟用 Microsoft Exchange 整合，請 Exchange In-Place 保留原則控制是否為位於 Exchange 的使用者啟用封存，並將其信箱置於 In-Place 保留狀態。 
  
如需有關封存原則如何運作（包括全域、網站及使用者原則的階層）的詳細資訊，請參閱[Plan for 封存 in 商務用 Skype Server](../../plan-your-deployment/archiving/archiving.md)。 如需如何在部署後管理原則的詳細資訊，請參閱[manage 封存原則 in 商務用 Skype Server](../../manage/archiving/policies.md)。
  
## <a name="global-policy"></a>全域原則

當您部署前端伺服器時，商務用 Skype Server 會建立一個全域原則進行封存。 預設會停用全域原則中的封存。 「全域」原則會控制是否對整個部署啟用內部和外部通訊的封存，除非您設定網站或使用者原則，以覆寫全域原則，或您使用 Microsoft Exchange 整合部分或所有使用者。 如果您使用 Microsoft Exchange 整合，全域原則不會套用到 Exchange 中的任何使用者，而且會將信箱置於 In-Place 保留狀態。
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>設定商務用 Skype Server 封存資料庫的封存全域原則

1. 使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 
    
3. 在左側導覽列中，依序按一下 **[監控和封存]** 和 **[封存原則]**。
    
4. 在 **[封存原則]** 頁面上，依序按一下 **[通用]** 和 **[編輯]**，然後按一下 **[顯示詳細資料]**。
    
5. 在 [編輯封存原則 - 通用] 中，執行下列動作：
    
   - 如果您不想要使用此預設全域名稱，請在 **[名稱]** 中指定全域原則的新名稱。 
    
   - 在 [ **描述**] 中，提供 (原則的相關資訊（例如，  *divisionName*  的全域原則）。
    
   - 若要控制未特別透過網站原則或使用者原則控制之所有網站及使用者的內部通訊封存，請選取或清除 **[封存內部通訊]** 核取方塊。
    
   - 若要控制未特別透過網站原則或使用者原則控制之所有網站及使用者的外部通訊封存，請選取或清除 [封存外部通訊] 核取方塊。
    
6. 按一下 **[認可]**。
    
## <a name="site-policies"></a>網站原則

您可以為每個網站建立封存原則，以啟用或停用特定網站的封存。 網站原則會覆寫全域原則，但使用者原則會覆寫網站原則。 僅當您不使用 microsoft Exchange 整合時，或若您使用 microsoft Exchange 整合，但有一些使用者不是位於 Exchange 上，且其信箱置於 In-Place 保留狀態，則僅適用封存原則。
  
### <a name="create-an-archiving-policy-for-a-site"></a>建立網站的封存原則

1. 使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。
    
3. 在左側導覽列中，依序按一下 **[監控和封存]** 和 **[封存原則]**。
    
    如需有關封存原則如何運作（包括全域、網站及使用者原則的階層）的詳細資訊，請參閱[Plan for 封存 in 商務用 Skype Server](../../plan-your-deployment/archiving/archiving.md)。
    
4. 按一下 [新增]，然後按一下 [站台原則]。
    
5. 在 [ **選取網站**] 中，按一下要套用原則的網站。
    
6. 在 **[新增封存原則]** 中，執行下列動作：
    
   - 在 [ **名稱**] 中，指定網站原則的名稱。 
    
   - 在 [ **描述**] 中，提供網站原則 (的相關資訊（例如，Redmond) 的網站原則）。
    
   - 若要控制指定網站的內部通訊封存，請選取或清除 [封存 **內部通訊** ] 核取方塊。
    
   - 若要控制指定網站的外部通訊封存，請選取或清除 [封存 **外部通訊** ] 核取方塊。
    
7. 按一下 **[認可]**。
    
## <a name="user-policies"></a>使用者原則

您可以為使用者建立和設定封存原則，然後將原則套用至特定的使用者或使用者群組，來啟用或停用特定使用者的封存。 使用者原則會覆寫任何全域原則或網站原則。 僅當您不使用 microsoft Exchange 整合時，或若您使用 microsoft Exchange 整合，但有一些使用者不是位於 Exchange 上，且其信箱置於 In-Place 保留狀態，則僅適用封存原則。
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>設定位於商務用 Skype Server 上之使用者的封存原則

1. 使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 
    
3. 在左側導覽列中，依序按一下 **[監控和封存]** 和 **[封存原則]**。
    
4. 依序按一下 **[新增]** 和 **[使用者原則]**。
    
5. 在 [新增封存原則] 中，執行下列動作：
    
   - 在 [名稱] 中，指定使用者原則的名稱。 
    
   - 在 [描述] 中，提供何謂使用者原則的相關資訊 (例如，適用於法務部門的使用者原則)。
    
   - 若要控制使用者原則的內部通訊封存，請選取或清除 [封存內部通訊] 核取方塊。
    
   - 若要控制使用者原則的外部通訊封存，請選取或清除 [封存外部通訊] 核取方塊。
    
6. 按一下 [認可]。
    
使用者原則僅會套用至您指派該原則的使用者。
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>將商務用 Skype Server 封存原則套用至使用者

1. 使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 
    
3. 在左導覽列中，按一下 **[使用者]**，然後搜尋想要設定的使用者帳戶。
    
4. 在列出搜尋結果的表格中，按一下使用者帳戶，並依序按一下 **[編輯]** 及 **[顯示詳細資料]**。
    
5. 在 [封存 **原則**] 下的 [**編輯商務用 Skype Server 使用者**] 中，選取您要套用的封存使用者原則。
    
    > [!NOTE]
    > **\<Automatic\>** 設定將套用預設伺服器安裝設定。 伺服器會自動套用這些設定。
  
6. 按一下 **[認可]**。
    

