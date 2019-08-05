---
title: 設定商務用 Skype Server 2015 使用整合連絡人存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
description: '摘要: 針對 Exchange Server 和商務用 Skype Server 設定整合連絡人存放區。'
ms.openlocfilehash: fd70c4b0b3d94ba26b76847ff053bf33d5902799
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188098"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>設定商務用 Skype Server 2015 使用整合連絡人存放區
 
**摘要:** 針對 Exchange Server 2016 或 Exchange Server 2013 及商務用 Skype Server 設定「整合連絡人存放區」。
  
使用者可以使用整合連絡人存放區來維護單一連絡人清單, 然後讓這些連絡人在多個應用程式 (包括商務用 Skype、Microsoft Outlook 2013 及 Microsoft Outlook Web App 2013) 中提供。 當您為使用者啟用整合連絡人存放區時, 該使用者的連絡人不會儲存在商務用 Skype 伺服器中, 並視需要進行檢索。 相反地, 他/她的連絡人會儲存在 Exchange Server 2016 或 Exchange Server 2013 中, 並使用 Exchange Web 服務進行檢索。
  
> [!NOTE]
> 從技術角度來看, 連絡人資訊是儲存在使用者的 Exchange 信箱中找到的一組資料夾中。 連絡人本身會儲存在名為「商務用 Skype 連絡人」的資料夾中, 使用者對使用者可見;連絡人的中繼資料儲存在使用者無法看見的子資料夾中。 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>為使用者啟用整合連絡人存放區

如果已設定商務用 Skype Server 與 Exchange Server 之間的伺服器對伺服器驗證, 則您也已啟用整合連絡人存放區;不需要額外的伺服器設定。 不過, 您需要額外的使用者帳戶設定, 才能將使用者的連絡人移至 [整合連絡人] 存放區。 根據預設, 使用者連絡人會保留在商務用 Skype 伺服器中, 而不是在整合的連絡人存放區中。
  
您可以使用商務用 Skype Server 使用者服務原則來管理整合連絡人存放區的存取權。 使用者伺服器原則只有單一屬性 (UcsAllowed);這個屬性是用來判斷使用者連絡人的儲存位置。 如果使用者是由使用者服務原則所管理, 而 UcsAllowed 已設定為 True ($True), 則使用者的連絡人會儲存在整合連絡人存放區中。 如果使用者是由使用者服務原則所管理, 而 UcsAllowed 已設定為 False ($False), 則他/她的連絡人將會儲存在商務用 Skype 伺服器中。
  
當您安裝商務用 Skype Server 時, 系統也會安裝單一使用者服務原則 (在全域範圍中設定)。 此原則中的 UcsAllowed 值會設定為 True, 這表示預設會將使用者連絡人儲存在整合連絡人存放區中 (假設已部署並設定)。 如果您想要將所有使用者連絡人遷移至 [整合連絡人] 商店, 您不需要執行任何動作。 
  
如果您不想將所有連絡人移至 [整合連絡人] 商店, 您可以將 [全域原則] 中的 [UcsAllowed] 屬性設為 False, 以停用所有使用者的整合連絡人存放區:
  
```
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

在全域原則中停用整合連絡人存放區之後, 您就可以建立可讓您使用整合連絡人存放區的每個使用者原則;這可讓您讓一些使用者將他們的連絡人保留在 [整合連絡人] 存放區中, 而其他使用者則能繼續在商務用 Skype Server 中保留他們的連絡人。 您可以使用類似以下的命令來建立每使用者使用者服務原則:
  
```
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

在您建立新原則之後, 您必須將該原則指派給應該有權存取整合連絡人存放區的任何使用者。 您可以使用類似以下的命令, 將每個使用者的原則指派給使用者:
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

指派原則之後, 商務用 Skype 伺服器將會開始將使用者的連絡人遷移至 [整合連絡人] 存放區。 完成遷移之後, 使用者就會將自己的連絡人儲存在 Exchange 中, 而不是儲存在商務用 Skype 伺服器中。 如果在遷移完成時, 使用者登入 Lync 2013, 就會出現一則訊息, 他/她會要求您登出商務用 Skype, 然後再次登入以完成程式。 未獲指派此每個使用者原則的使用者, 將不會將其連絡人遷移至 [整合連絡人] 存放區。 這是因為這些使用者是由全域原則所管理, 而「整合連絡人存放區」已在全域原則中停用。
  
您可以從商務用 Skype Server Management Shell 中執行[Test CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) Cmdlet, 以驗證使用者的連絡人是否已順利遷移到整合連絡人存放區:
  
```
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

如果 CsUnifiedContactStore 成功, 則表示使用者 sip 的連絡人: kenmyer @<span></span>litwareinc<span></span>已遷移至整合連絡人存放區。
  
## <a name="rolling-back-the-unified-contact-store"></a>回退整合連絡人存放區

如果您需要從 [整合連絡人] 存放區中移除使用者的連絡人 (例如, 如果使用者需要在 Microsoft Lync Server 2010 上 rehomed, 因此不能再使用 [整合連絡人] 存放區), 您必須執行兩個動作。 首先, 您必須為使用者指派新的使用者服務原則, 該原則禁止在整合連絡人存放區中儲存連絡人。 (也就是 UcsAllowed 屬性已設為 $False 的原則)。如果您沒有這樣的原則, 您可以使用類似以下的命令來建立一個原則:
  
```
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

然後, 您可以使用如下所示的命令來指派這個新的每個使用者原則 (NoUnifiedContactStore):
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

上述命令會將新的原則指派給使用者 Ken Myer, 同時也會防止 Ken 的連絡人遷移到整合連絡人存放區。
  
> [!NOTE]
> 在某些情況下, 您只要取消指派使用者目前的使用者服務原則, 就能達到相同的網路效果。 例如, 假設 Ken Myer 的每個使用者服務原則都是啟用整合連絡人存放區, 但是您的全域原則禁止使用整合連絡人存放區。 在這種情況下, 您可以取消指派 Ken 的每個使用者服務原則。 當您執行此動作時, 系統會自動由全域原則管理, 因此將不再擁有對整合連絡人存放區的存取權。 若要取消指派先前指派的每個使用者原則, 請使用與前面所示的相同命令, 但這次將 PolicyName 參數設定為 null 值: Grant-CsUserServicesPolicy 身分 "Ken Myer"-PolicyName $Null 
  
在使用 [整合連絡人存放區] 時, 請務必記住「防止 Ken 連絡人遷移到整合連絡人存放區」這一術語。 只要將 Ken 指派給新的使用者服務原則, 就不會將自己的連絡人移出 [整合連絡人] 存放區。 當使用者登入商務用 Skype Server 時, 系統會檢查使用者的使用者服務原則, 以查看他/她的連絡人是否應該保留在 [整合連絡人] 存放區中。 如果答案是 [是] (也就是 UcsAllowed 屬性設為 [$True]), 這些連絡人將會遷移至 [整合連絡人] 存放區 (假設這些連絡人不在 [整合連絡人] 存放區中)。 如果答案為 [否], 則商務用 Skype Server 就會忽略使用者的連絡人, 並移至其下一個工作。 也就是說, 不論 UcsAllowed 屬性的值為何, 商務用 Skype 伺服器不會自動將使用者的連絡人從整合連絡人存放區移出。
  
這也表示將使用者指派給新的使用者服務原則之後, 您必須執行[CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/invoke-csucsrollback?view=skype-ps) Cmdlet, 以便將使用者的連絡人從 Exchange Server 移出並回到商務用 Skype 伺服器。 例如, 將 Ken Myer 指派給新的使用者服務原則之後, 您就可以使用下列命令, 將其連絡人移出 [整合連絡人] 存放區:
  
```
Invoke-CsUcsRollback -Identity "Ken Myer"
```

如果您變更使用者服務原則, 但不執行 CsUcsRollback Cmdlet Ken 的連絡人, 則不會從整合連絡人存放區中移除。 如果您執行的是 Invoke CsUcsRollback, 但不會變更 Ken Myer 的使用者服務原則, 該怎麼辦？ 在這種情況下, Ken 連絡人將會暫時從整合連絡人存放區中移除。 這個移除是臨時性的, 這項功能很重要, 請務必記住這一點。 從 [整合連絡人] 存放區移除 Ken 連絡人後, 商務用 Skype 伺服器將會等候7天, 然後檢查已指派給 Ken 的使用者服務原則。 如果 Ken 仍獲指派可讓整合連絡人存放區使用者使用的原則, 則他的連絡人會自動移回連絡人存放區中。 若要從 [整合連絡人] 存放區永久移除連絡人, 除了執行 CsUcsRollback Cmdlet 之外, 您還必須變更使用者服務原則。
  
由於有大量可影響遷移的變數, 所以很難估計帳戶完全遷移到整合連絡人存放區之前所需的時間。 但作為一般規則, 遷移不會立即生效: 即使遷移少量的連絡人, 移動作業也可能需要10分鐘或更長的時間才能完成。
  

