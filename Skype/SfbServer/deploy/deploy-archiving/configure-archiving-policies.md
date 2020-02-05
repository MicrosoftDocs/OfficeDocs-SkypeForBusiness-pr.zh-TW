---
title: 設定商務用 Skype Server 的存檔原則
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
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 摘要：請閱讀本主題，以瞭解如何針對商務用 Skype Server 使用者設定初始歸檔原則。
ms.openlocfilehash: ff946fe2fde2fcd8aae842e809a89bffb7852bca
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769206"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a>設定商務用 Skype Server 的存檔原則
 
**摘要：** 請閱讀本主題，以瞭解如何針對商務用 Skype Server 使用者設定初始歸檔原則。
  
在商務用 Skype Server 中，您可以使用原則來針對託管于商務用 Skype Server 的使用者啟用和停用內部通訊與外部通訊的封存。 這包括下列各項：
  
- 當您部署商務用 Skype Server 時預設建立的全域原則
    
- 選擇性的網站層級原則，可指定如何針對特定網站執行歸檔
    
- 指定如何針對特定使用者執行歸檔的選擇性使用者層級原則
    
您最初是在部署封存時設定封存原則，但是您可以在部署之後變更、新增及刪除原則。 在商務用 Skype Server 的 [控制台] 中，您可以使用 [封存**與監控**] 群組的 [**存檔原則**] 頁面，來管理全域、網站和使用者層級的原則。
  
> [!NOTE]
> 若要控制封存的實現，您必須指定選項，例如是否要封存 IM 或會議、使用重要模式，以及清除選項。 根據預設，全域存檔設定或任何網站或池封存設定中不會啟用任何選項。 您應該先指定所有適當的選項，才能啟用內部或外部通訊的封存。 如需詳細資訊，請參閱[設定商務用 Skype Server 的存檔選項](configure-archiving-options.md)。 
  
> [!NOTE]
> 如果您針對您的部署啟用 Microsoft Exchange 整合，Exchange 就地保留原則會控制是否針對託管于 Exchange 的使用者啟用封存，並將其信箱放在就地保留中。 
  
如需有關歸檔原則運作方式的詳細資料，包括全域、網站和使用者原則的階層，請參閱[在商務用 Skype 伺服器中進行封存規劃](../../plan-your-deployment/archiving/archiving.md)。 如需如何在部署之後管理原則的詳細資料，請參閱[管理商務用 Skype Server 中的存檔原則](../../manage/archiving/policies.md)。
  
## <a name="global-policy"></a>全域原則

當您部署前端伺服器時，商務用 Skype 伺服器會建立一個全域原則來存檔。 根據預設，會停用全域原則中的封存。 全域原則會控制是否針對整個部署啟用封存，除非您設定網站或使用者原則，而這會覆寫全域原則，或是您針對部分或全部使用 Microsoft Exchange 整合您的使用者。 如果您使用的是 Microsoft Exchange 整合，全域原則就不會套用至任何託管于 Exchange 的使用者，並將信箱放在就地保留中。
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>針對商務用 Skype Server 封存資料庫設定存檔的全域原則

1. 從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 
    
3. 在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**原則**]。
    
4. 在 [**存檔原則**] 頁面上，按一下 [**全域**]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。
    
5. 在 [**編輯封存原則-全域**] 中，執行下列動作：
    
   - 在 [**名稱**] 中，如果您不想使用預設的全域名稱，請指定全域原則的新名稱。 
    
   - 在 [**描述**] 中，提供原則的相關資訊（例如， *divisionName*的全域原則）。
    
   - 若要控制未透過網站原則或使用者原則專門控制之所有網站和使用者的內部通訊的封存，請選取或清除 [封存**內部通訊**] 核取方塊。
    
   - 若要控制未透過網站原則或使用者原則專門控制之所有網站和使用者的外部通訊的封存，請選取或清除 [封存**外部通訊**] 核取方塊。
    
6. 按一下 [認可]****。
    
## <a name="site-policies"></a>網站原則

您可以針對特定網站，建立每個網站的存檔原則來啟用或停用其封存。 網站原則會覆寫全域原則，但使用者原則會覆寫網站原則。 如果您不使用 Microsoft Exchange 整合，或如果您使用的是 Microsoft Exchange 整合，但不是駐留在 Exchange 上並讓其信箱放在就地保留中的一些使用者，則只適用存檔原則。
  
### <a name="create-an-archiving-policy-for-a-site"></a>建立網站的存檔原則

1. 從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**原則**]。
    
    如需有關歸檔原則運作方式的詳細資料，包括全域、網站和使用者原則的階層，請參閱[在商務用 Skype 伺服器中進行封存規劃](../../plan-your-deployment/archiving/archiving.md)。
    
4. 按一下 [新增]****，然後按一下 [站台原則]****。
    
5. 在 [**選取網站**] 中，按一下要套用原則的網站。
    
6. 在**新**的 [封存原則] 中，執行下列動作：
    
   - 在 [**名稱**] 中，指定網站原則的名稱。 
    
   - 在 [**描述**] 中，提供網站原則的相關資訊（例如，雷蒙德的網站原則）。
    
   - 若要控制指定網站內部通訊的歸檔，請選取或清除 [封存**內部通訊**] 核取方塊。
    
   - 若要控制指定網站外部通訊的存檔，請選取或清除 [封存**外部通訊**] 核取方塊。
    
7. 按一下 [認可]****。
    
## <a name="user-policies"></a>使用者原則

您可以為使用者建立及設定存檔原則，然後將原則套用到特定的使用者或使用者群組，以啟用或停用特定使用者的封存。 使用者原則會覆寫任何全域原則或網站原則。 如果您不使用 Microsoft Exchange 整合，或如果您使用的是 Microsoft Exchange 整合，但不是駐留在 Exchange 上並讓其信箱放在就地保留中的一些使用者，則只適用存檔原則。
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>針對駐留在商務用 Skype Server 上的使用者設定存檔原則

1. 從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 
    
3. 在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**原則**]。
    
4. 依序按一下 [新增]**** 和 [使用者原則]****。
    
5. 在**新**的 [封存原則] 中，執行下列動作：
    
   - 在 [**名稱**] 中，指定使用者原則的名稱。 
    
   - 在 [**描述**] 中，提供使用者原則的相關資訊（例如，法律部門的使用者原則）。
    
   - 若要控制使用者原則的內部通訊的歸檔，請選取或清除 [封存**內部通訊**] 核取方塊。
    
   - 若要控制使用者原則的外部通訊的存檔，請選取或清除 [封存**外部通訊**] 核取方塊。
    
6. 按一下 [認可]****。
    
使用者原則只適用于您指派原則的使用者。
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>將商務用 Skype 伺服器歸檔原則套用至使用者

1. 從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 
    
3. 在左側導覽列中，按一下 [**使用者**]，然後搜尋您要設定的使用者帳戶。
    
4. 在列出搜尋結果的表格中，依序按一下使用者帳戶、[編輯]**** 及 [顯示詳細資料]****。
    
5. 在 [**存檔原則**] 底下的 [**編輯商務用 Skype Server 使用者**] 中，選取您要套用的存檔使用者原則。
    
    > [!NOTE]
    > [ ** \<自動\> **設定] 會套用預設伺服器安裝設定。 伺服器會自動套用這些設定。
  
6. 按一下 [認可]****。
    

