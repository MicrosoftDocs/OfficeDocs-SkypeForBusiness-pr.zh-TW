---
title: '管理商務用 Skype Server 中的電話撥入式會議存取號碼 '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 摘要：瞭解如何管理商務用 Skype Server 中的電話撥入式會議存取號碼。
ms.openlocfilehash: 868d757edc6728254c1ab09d22398cd3dc60901b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806483"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a>管理商務用 Skype Server 中的電話撥入式會議存取號碼
 
**摘要：** 瞭解如何管理商務用 Skype Server 中的電話撥入式會議存取號碼。
  
當您部署電話撥入式會議時，您必須設定使用者可以從公用交換電話網路 (PSTN) 撥打的電話號碼，以加入會議的音訊部分。 這些撥入存取號碼會顯示在會議邀請和電話撥入式會議設定網頁上。 
  
本主題說明如何查看、修改或刪除現有的電話撥入式會議存取號碼。 如需如何建立初始撥入存取號碼的詳細資訊，請參閱 [在商務用 Skype Server 中設定電話撥入式會議](../../deploy/deploy-conferencing/dial-in-conferencing.md)。
  
## <a name="view-dial-in-conferencing-access-numbers"></a>查看電話撥入式會議存取號碼

您可以使用商務用 Skype Server 控制台或使用商務用 Skype Server 管理命令介面來查看電話撥入式會議存取號碼。
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台來查看撥入存取號碼

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 控制台。
    
3. 在左導覽列中，按一下 [會議]，然後按一下 [撥入存取號碼]。
    
4. 在 **[撥入存取號碼]** 頁面中，按一下要檢視的存取號碼。
    
5. 在 [ **編輯**] 中，選取 [ **顯示詳細資料** ] 核取方塊。
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面來查看撥入存取號碼

若要查看撥入存取號碼的資訊，請使用 **Get-CsDialInConferencingAccessNumber** Cmdlet。
  
下列命令會傳回設定供組織使用之所有電話撥入式會議存取號碼的集合： 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

以下是傳回之資訊類型的範例：
  
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

如需詳細資訊，請參閱 [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。
  
## <a name="modify-dial-in-conferencing-access-numbers"></a>修改電話撥入式會議存取號碼

您可以使用商務用 Skype Server 控制台或使用商務用 Skype Server 管理命令介面來修改撥入存取號碼。
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台修改撥入存取號碼

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 控制台。
    
3. 在左導覽列中，按一下 [會議]，然後按一下 [撥入存取號碼]。
    
4. 在 [ **撥入存取號碼** ] 頁面上，按一下清單中的其中一個撥入存取號碼，按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。
    
    > [!NOTE]
    > 使用搜尋欄位來搜尋撥入存取號碼清單中可能無法產生預期結果的欄內容。請依照您想要的欄排序此清單，找出您想檢視或變更的撥入存取號碼。 
  
5. 在 [ **顯示號碼**] 中，輸入公用交換電話網路 (PSTN) 電話使用者撥號以加入會議的電話號碼。 
    
    此號碼會顯示在會議邀請中和電話撥入式會議設定網頁上。
    
6. 在 [ **顯示名稱**] 中，輸入撥入存取號碼的描述。 這是商務用 Skype 搜尋結果中與撥入存取號碼相關聯的名稱。
    
    當使用者呼叫存取號碼時，此名稱會顯示在用戶端中。 
    
7. 在 [ **行 uri**] 中，輸入電話 uri 格式的撥入存取號碼的 e.164 號碼，包含號碼前面的 + 符號，並排除空格。 例如電話： + 14255550200。
    
    > [!NOTE]
    > 其他電話撥入式會議存取號碼無法重複使用相同的列 URI。 
  
8. 在 [ **SIP URI**] 中，執行下列動作：
    
   在文字方塊中，輸入此撥入式會議存取號碼的唯一 SIP URI。 這種 SIP URI 會顯示在不同的位置，包括（但不限於）來電通知訊息和舊版的 Lync 用戶端。
    
    > [!NOTE]
    > 其他電話撥入式會議存取號碼無法重複使用相同的 SIP URI。 建立存取號碼之後，便無法修改 SIP URI。 變更 SIP URI 的唯一方法是刪除並重新建立存取號碼。 
  
   在下拉式清單方塊中，按一下支援此撥入存取號碼之會議應答應用程式的網域。
    
9. 在 [ **集** 區] 中，按一下執行支援此撥入存取號碼之會議助理實例的集區。
    
    > [!NOTE]
    > 如果您在建立存取號碼之後需要變更集區，則必須使用 **Move-CsApplicationEndpoint** Cmdlet，或刪除並重新建立存取號碼。
  
10. 在 [ **主要語言**] 中，按一下為此撥入存取號碼播放提示時所使用的語言。 
    
    主要語言是會議助理用來接聽通話的語言。 在 [電話撥入式會議設定] 網頁上的每一個存取電話號碼旁會顯示支援的語言。
    
11.  (選用) 在 **次要語言中 (最多四個)**，請按一下 [ **新增**]，選取您要支援的來電者撥打此撥入存取號碼的一或多個其他語言，然後按一下 **[確定]**。 
    
    您最多可以為每個撥入存取號碼選擇四種次要語言。 使用者在撥入會議時，可以先選取次要語言，再進入會議識別碼。
    
12. 若要新增撥入存取號碼的地區，請在 [ **關聯的地區**] 下，按一下 [ **新增**]，然後按一下與此撥入存取號碼的撥號對應表相關聯的一個或多個地區，然後按一下 **[確定]**。
    
13. 若要從撥入存取號碼中刪除地區，請在 [ **關聯的地區**] 下，按一下您要刪除的地區，然後按一下 [ **移除**]。
    
14. 按一下 **[認可]**。
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面來修改撥入存取號碼

若要修改撥入存取號碼，請使用 **Set-CsDialInConferencingAccessNumber** Cmdlet。
  
下列命令會以 Identity sip:RedmondDialIn@litwareinc.com 修改電話撥入式會議存取號碼的 DisplayName 屬性。 在此範例中，顯示名稱設為 "Redmond Dial-In 存取號碼"：
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

在下一個範例中，會修改身分識別 sip:RedmondDialIn@litwareinc.com 的電話撥入式會議存取號碼，以包含兩個地區： Redmond 和西雅圖。 為達此目的，會先呼叫 Region 參數，然後是兩個地區 (以逗號分隔的兩個字串值)。 請注意，除非已經在撥號對應表中定義 Redmond 和 Seattle 地區，否則這個命令將會失敗。
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

如需詳細資訊，請參閱 [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)。
  
## <a name="delete-a-dial-in-conferencing-access-number"></a>刪除電話撥入式會議存取號碼

您可以使用商務用 Skype Server 控制台或使用商務用 Skype Server 管理命令介面來刪除電話撥入式會議存取號碼。
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台刪除電話撥入式會議存取號碼

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。
    
2.  開啟商務用 Skype Server 控制台。
    
3. 在左導覽列中，按一下 [會議]，然後按一下 [撥入存取號碼]。
    
4. 在頁面中，按一下清單中要刪除的撥入號碼，按一下 **[編輯]**，再按一下 **[刪除]**。
    
5. 按一下 **[確定]**。
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面來刪除電話撥入式會議存取號碼

若要刪除電話撥入式會議存取號碼，請使用 **Remove-CsDialInConferencingAccessNumber**。
  
下列命令會刪除具有 Identity sip:RedmondDialInAccess@litwareinc.com 的電話撥入式會議存取號碼：
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

下一個命令會刪除與西北地方相關聯的所有電話撥入式會議存取號碼：
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

下一個命令會刪除所有以義大利文言為主要語言的電話撥入式會議存取號碼：
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

如需詳細資訊，請參閱 [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps)。
  

