---
title: 自訂商務用 Skype Server 的使用者帳戶屬性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: 您可以使用本節中的程式來修改個別的使用者帳戶屬性。
ms.openlocfilehash: eca88717d0b81ddd7c27fc140df9bdbf7590c5c6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991428"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>自訂商務用 Skype Server 的使用者帳戶屬性
 
您可以使用本節中的程式來修改個別的使用者帳戶屬性。
  
您可以在個別使用者層級完成兩個基本作業：
  
- [針對特定的使用者帳戶設定電話選項](customize-properties.md#Tel_Op)
    
- [將使用者移至另一個資源區](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>針對特定的使用者帳戶設定電話選項
<a name="Tel_Op"> </a>

您可以自訂特定使用者的電話設定（只要個別使用者已啟用商務用 Skype 伺服器且組織支援電話語音）。
  
商務用 Skype Server 使用者電話選項包括下列各項：
  
- **音訊/視頻已停用**使用者無法使用音訊和影片進行通話。
    
- **僅限 pc 至電腦**使用者只能進行 PC 對電腦音訊或視頻通話。
    
- **企業語音**使用者可以使用商務用 Skype 伺服器基礎結構來傳送所有來電和撥出電話。 使用者也可以進行 PC 對電腦通話。
    
- **遠端通話控制**使用者可以使用商務用 Skype Server 來控制桌面電話，也可以進行 PC 對電腦通話。
    
如需有關為組織設定電話語音的詳細資訊，請參閱在[商務用 Skype server 中啟用企業語音的使用者](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)，以及在部署檔中[部署商務用 skype 伺服器中的企業語音](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)。
  
1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 
    
3. 在左側導覽列中，按一下 [**使用者**]。
    
4. 在 [**搜尋使用者**] 方塊中，輸入您想要的 [顯示名稱]、[名字]、[姓氏]、[安全帳戶管理員] （SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。
    
5. 在表格中，按一下您要修改的使用者帳戶。
    
6. 按一下 [**編輯**] 功能表上的 [**修改**]。
    
7. 在 [**電話**] 中，執行下列動作：
    
   - 若要停用使用者的音訊和視頻通話，請按一下 [**音訊/視頻停用**]。
    
   - 若要為使用者啟用 PC 對電腦音訊通訊，但不啟用遠端通話控制或企業語音，請按一下 [**僅電腦至電腦**]。 針對使用者在 pc 對電腦音訊通訊所用的電話，指定**行 URI**的值。
    
   - 若要使用商務用 Skype 基礎結構來傳送使用者的電話，請依照服務類別（包括 PC 對電腦音訊通訊），按一下 [**企業語音**]。 在 [**行 URI**] 中，指定企業語音的電話號碼。 在 [**撥號計畫原則**] 和 [**語音原則**] 中，為使用者指定適當的原則。 若要指定將使用者撥打的電話號碼轉換為 e. 164 格式的正常化規則，請在**位置原則**中選取適當的位置設定檔。
    
   - 若要啟用遠端通話控制，讓使用者能夠從商務用 Skype 伺服器控制其桌面電話線路，以進行 PC 對電腦通話和 PC 到電話的通話，請按一下 [**遠端通話控制**]。 在 [**行 URI**] 中，指定遠端通話控制的電話號碼。 使用者必須有桌面手機和私人分支 exchange （PBX）連線才能進行呼叫路由。
    
## <a name="move-users-to-another-pool"></a>將使用者移至另一個資源區
<a name="Move_Users"> </a>

您可以使用商務用 Skype Server 的 [控制台]，將使用者指派給特定的伺服器或文件庫。
  
> [!TIP]
> 將所有現有使用者從執行 Lync Server 2010 或較舊版本的來源池移至複雜的 Active Directory 環境中的商務用 Skype Server 目標池，可能會導致較慢的 Active Directory 複製。 若要避免這種情況，您可以使用搜尋篩選器，從執行 Lync Server 2010 或較舊版本的 pool 中移動使用者，或者您可以使用商務用 Skype Server Management Shell，以使用 Cmdlet 來移動使用者。 此外，篩選功能也可與商務用 Skype 伺服器使用者搭配使用。 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>若要將選取的使用者移至不同的伺服器或文件庫

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。  
    
3. 在左側導覽列中，按一下 [**使用者**]。
    
4. 在 [**搜尋使用者**] 方塊中，輸入您想要的 [顯示名稱]、[名字]、[姓氏]、[安全帳戶管理員] （SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。 
    
5. 在表格中，選取清單中特定的使用者或使用者。 
    
6. 在 [**動作**] 功能表上，按一下 [**將選取的使用者移至資源庫**]。
    
7. 在 [**移動使用者**] 中，選取您要在 [**目的地註冊機構**] 中將使用者移至哪個池。
    
8. 可選如果目的地伺服器或池無法使用，請選取 [**強制**] 核取方塊。
    
    > [!CAUTION]
    > 如果您選取 [**強制**]，使用者帳戶就會移動，但任何相關聯的使用者資料都會被刪除（例如，使用者已排程的會議）。 如果您不選取它，就會移動帳戶和相關聯的資料。 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>將所有使用者從一個伺服器或文檔池移至另一個伺服器或文檔池中

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。  
    
3. 在左側導覽列中，按一下 [**使用者**]。
    
4. 在 [**動作**] 功能表上，按一下 [**將所有使用者移至資源庫**]。
    
5. 在 [**移動使用者**] 中，選取包含您要在 [**來源註冊機構] 池中**移動之使用者帳戶的池。
    
6. 在 [**目的地註冊機構] 池中**，選取您要將使用者移至哪個池。
    
7. 可選如果目的地伺服器或池無法使用，請選取 [**強制**] 核取方塊。
    
    > [!CAUTION]
    > 如果您選取 [**強制**]，使用者帳戶就會移動，但任何相關聯的使用者資料都會被刪除（例如，使用者已排程的會議）。 如果您不選取它，就會移動帳戶和相關聯的資料。 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>使用篩選將使用者從一個池中移到另一個池

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 
    
3. 在左側導覽列中，按一下 [**使用者**]。
    
4. 在 [**使用者搜尋**] 中，按一下 [**搜尋**]，然後按一下 [**新增篩選**]。
    
5. 在搜尋準則中，選取 [**註冊機構池**]，選取 [**等於**]，選取 [**目前池 FQDN**]，然後按一下 [**尋找**]。
    
6. 在 [**動作**] 功能表上，按一下 [**將所有使用者移至資源庫**]。
    
    > [!NOTE]
    > 當篩選套用至現有的一組使用者時，會在篩選的使用者子集的內容（而非**所有**可能的使用者）中，選擇 [**將所有使用者移至資源庫**]。
  
7. 在 [**移動使用者**] 中，選取包含您要在 [**來源註冊機構] 池中**移動之使用者帳戶的池。
    
8. 在 [**目的地註冊機構] 池中**，選取您要移動使用者的池。
    
9. 可選如果目的地伺服器或池無法使用，請選取 [**強制**] 核取方塊。
    
    > [!CAUTION]
    > 如果您選取 [**強制**]，使用者帳戶就會移動，但任何相關聯的使用者資料都會被刪除（例如，使用者已排程和連絡人的會議）。 如果您不選取它，就會移動帳戶和相關聯的資料。 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>使用 Windows Powershell Cmdlet 將使用者從一個池中移至另一個池

1. 視您執行的是 Windows PowerShell 命令（本機或遠端）而定，您需要以正確的商務用 Skype Server 系統管理角色的成員身分登入，如下所示：
    
   是. 如果您是在本機電腦上執行命令（例如，直接登入前端伺服器）：登入商務用 Skype Server Management Shell 的電腦是以 RTCUniversalServerAdmins 群組的成員或必要的使用者許可權來安裝，如**委派設定許可權**中所述。
    
   乙. 如果您是在另一部電腦遠端執行命令（例如，登入您的電腦，並在標準版前端伺服器上遠端執行命令）：從指派給 CsUserAdministrator 角色或 CsAdministrator 的使用者帳戶。角色，請登入內部部署中的任何電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：請依序按一下 [**開始**]、[**所有程式**]、[**商務用 skype**]，然後按一下 [**商務用 skype server 管理命令**介面]。
    
3. 若要移動單一使用者，請使用 Move-csuser Cmdlet，如下所示：
    
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    使用者要移動的使用者是 Pilar 方，而使用者會從目前指派的主池中移至 [資源庫] pool01.contoso.net
    
4. 若要移動大量的使用者，請使用**move-csuser** Cmdlet 的篩選器，並將產生的使用者組傳遞到**move-csuser**：
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    **Move-csuser**和**move-csuser**的合併命令可能會造成下列情況：
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


