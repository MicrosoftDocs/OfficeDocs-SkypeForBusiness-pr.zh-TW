---
title: '管理商務用 Skype Server 中的電話撥入式會議存取號碼 '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: '摘要: 瞭解如何在商務用 Skype Server 中管理電話撥入式會議存取號碼。'
ms.openlocfilehash: e41011c4ba06da7f05d8cb1a52717e707cd2f8bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191275"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a>管理商務用 Skype Server 中的電話撥入式會議存取號碼
 
**摘要:** 瞭解如何在商務用 Skype Server 中管理電話撥入式會議存取號碼。
  
當您部署電話撥入式會議時, 您必須設定使用者可從公用交換電話網絡 (PSTN) 撥打電話的電話號碼, 以加入會議的音訊部分。 這些撥入存取號碼會出現在會議邀請和 [電話撥入式會議設定] 網頁上。 
  
本主題說明如何查看、修改或刪除現有的電話撥入式會議存取號碼。 如需如何建立初始撥入存取號碼的詳細資訊, 請參閱[在商務用 Skype Server 中設定電話撥入式會議](../../deploy/deploy-conferencing/dial-in-conferencing.md)。
  
## <a name="view-dial-in-conferencing-access-numbers"></a>查看電話撥入式會議存取號碼

您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server Management Shell 來查看電話撥入式會議存取號碼。
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 來查看撥入存取號碼

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中, 按一下 [**會議**], 然後按一下 [**撥入存取號碼**]。
    
4. 在 [**撥入存取號碼**] 頁面上, 按一下您要查看的存取號碼。
    
5. 在 [**編輯**] 中, 選取 [**顯示詳細資料**] 核取方塊。
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 來查看撥入存取號碼

若要查看電話撥入存取號碼的相關資訊, 請使用**CsDialInConferencingAccessNumber** Cmdlet。
  
下列命令會傳回已設定為在組織中使用的所有電話撥入式會議存取號碼集合: 
  
```
Get-CsDialInConferencingAccessNumber
```

下列是傳回的資訊類型範例:
  
<pre>
Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                     CN=Application Contacts,CN=RTCService=Services,
                     CN=Configuration,DC=litwareinc,DC=com
PrimaryUri         : sip:testnumber@litwareinc.com
DisplayName        : Test
DisplayNumber      : 1-425-555-1019
LineUri            : tel:+14255551019
PrimaryLanguage    : en-US
SecondaryLanguages : {}
Pool               : atl-cs-001.litwareinc.com
HostingProvider    :
Regions            : {US}
</pre>

如需詳細資訊, 請參閱[CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。
  
## <a name="modify-dial-in-conferencing-access-numbers"></a>修改電話撥入式會議存取號碼

您可以使用商務用 Skype Server 的 [控制台] 或 [商務用 Skype Server Management 命令介面] 來修改撥入存取號碼。
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 修改撥入存取號碼

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中, 按一下 [**會議**], 然後按一下 [**撥入存取號碼**]。
    
4. 在 [**撥入存取號碼**] 頁面上, 按一下清單中的其中一個撥入存取號碼, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。
    
    > [!NOTE]
    > 使用 [搜尋] 欄位來搜尋撥入存取號碼清單中的欄內容, 可能不會產生您預期的結果。 您可以改為依您想要查看或變更的撥入存取號碼來排序清單。 
  
5. 在 [**顯示號碼**] 中, 輸入「公用交換電話網絡 (PSTN) 電話撥打電話給」加入會議的電話號碼。 
    
    這個數位會顯示在 [會議邀請] 和 [電話撥入式會議設定] 網頁上。
    
6. 在 [**顯示名稱**] 中, 輸入撥入存取號碼的描述。 這是與商務用 Skype 搜尋結果中的撥入存取號碼相關聯的名稱。
    
    當使用者呼叫存取號碼時, 此名稱就會顯示在用戶端中。 
    
7. 在 [**行 uri**] 中, 輸入電話 uri 格式的撥入存取號碼的 E. 164 個數字, 包括數位前面的 + 符號, 不含空格。 例如, 電話: + 14255550200。
    
    > [!NOTE]
    > 其他電話撥入式會議存取號碼無法重複使用相同的行 URI。 
  
8. 在**SIP URI**中, 請執行下列動作:
    
   在文字方塊中, 輸入此電話撥入式會議存取號碼的唯一 SIP URI。 此 SIP URI 會顯示在不同的位置, 包括但不限於呼叫通知訊息及舊版 Lync 用戶端版本。
    
    > [!NOTE]
    > 其他電話撥入式會議存取號碼無法重複使用相同的 SIP URI。 在建立存取號碼之後, 便無法修改 SIP URI。 變更 SIP URI 的唯一方式是刪除並重新建立存取號碼。 
  
   在下拉式清單方塊中, 按一下支援此撥入存取號碼之會議助理應用程式的網域。
    
9. 在 [Pool] (**池**) 中, 按一下執行支援此撥入存取號碼之會議助理實例的池。
    
    > [!NOTE]
    > 如果您在建立存取號碼後需要變更池, 您必須使用**CsApplicationEndpoint** Cmdlet, 或刪除並重新建立存取號碼。
  
10. 在**主要語言**中, 按一下針對此撥入存取號碼播放提示的語言。 
    
    主要語言是會議助理用來接聽通話的語言。 支援的語言會顯示在電話撥入式會議設定網頁上的每個存取電話號碼旁邊。
    
11. 可選在**次要語言 (最多四個)** 中, 按一下 [**新增**], 選取您想要支援來電者至此撥入存取號碼的一或多個其他語言, 然後按一下 **[確定]**。 
    
    您最多可以為每個撥入存取號碼選擇四個次要語言。 使用者在撥入會議時, 輸入會議 ID 前, 就可以選取次要語言。
    
12. 若要新增撥入存取號碼的地區, 請在 [**相關區域**] 底下, 按一下 [**新增**], 按一下與此撥入存取號碼的撥號方案相關聯的一個或多個區域, 然後按一下 **[確定]**。
    
13. 若要從撥入存取號碼刪除區域, 請在 [**相關區域**] 底下, 按一下您要刪除的區域, 然後按一下 [**移除**]。
    
14. 按一下 [認可]****。
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 來修改撥入存取號碼

若要修改撥入存取號碼, 請使用**CsDialInConferencingAccessNumber** Cmdlet。
  
下列命令會使用身分識別 sip:RedmondDialIn@litwareinc.com 來修改電話撥入式會議存取號碼的 DisplayName 屬性。 在這個範例中, 顯示名稱會設定為「雷德撥入存取號碼」:
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

在下一個範例中, 含有身分識別 sip:RedmondDialIn@litwareinc.com 的電話撥入式會議存取號碼已修改, 以包含兩個地區: 雷蒙德與北京。 若要這樣做, 請先呼叫 [地區] 參數, 接著再加上兩個區域 (以逗號分隔的兩個字串值)。 請注意, 除非雷德蒙及西雅圖地區都已在撥號方案中定義, 否則此命令將會失敗。
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

如需詳細資訊, 請參閱[設定 CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)。
  
## <a name="delete-a-dial-in-conferencing-access-number"></a>刪除電話撥入式會議存取號碼

您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server 管理命令介面, 刪除電話撥入式會議存取號碼。
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 刪除電話撥入式會議存取號碼

1.  從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦.
    
2.  開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中, 按一下 [**會議**], 然後按一下 [**撥入存取號碼**]。
    
4. 在頁面上, 按一下清單中您要刪除的撥入號碼, 按一下 [**編輯**], 然後按一下 [**刪除**]。
    
5. 按一下 [確定]****。
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 刪除電話撥入式會議存取號碼

若要刪除電話撥入式會議存取號碼, 請使用 [**移除-CsDialInConferencingAccessNumber**]。
  
下列命令會刪除含身分識別 sip:RedmondDialInAccess@litwareinc.com 的電話撥入式會議存取號碼:
  
```
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

[下一步] 命令會刪除與西北地方相關的所有電話撥入式會議存取號碼:
  
```
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

[下一步] 命令會刪除所有以義大利為主要語言的電話撥入式會議存取號碼:
  
```
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

如需詳細資訊, 請參閱[移除-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps)。
  

