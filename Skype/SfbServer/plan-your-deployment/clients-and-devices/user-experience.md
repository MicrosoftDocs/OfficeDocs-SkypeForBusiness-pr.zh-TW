---
title: 規劃使用者的商務用 Skype 2015 用戶端體驗
ms.author: v-mahoffman
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: 摘要：瞭解新的商務用 Skype，以及您可以採取的步驟，以準備您的環境和使用者進行更新，不論是使用商務用 Skype 線上，商務用 Skype Server 2019，商務用 Skype Server 2015，lync server 2013，還是 lync server 2010。
ms.openlocfilehash: a35a447d9810952e9aac149f2297eda87575bdf3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740454"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>規劃使用者的商務用 Skype 2015 用戶端體驗
 
**摘要：** 深入瞭解新的商務用 Skype，以及您可以採取的步驟，以準備您的環境和使用者進行更新，不論是使用商務用 Skype 線上、商務用 Skype Server 2019、商務用 Skype Server 2015、lync server 2013，還是 lync server 2010。
  
Lync 2013 的2015年4月14日 Office 更新包含新的商務用 Skype 使用者介面。 此項更新可讓系統管理員控制用戶端的外觀與風格，並選擇要保留 Lync 2013 用戶端經驗，還是使用改良的商務用 Skype 用戶端經驗。 商務用 Skype 用戶端會有效地取代 Lync 2013 用戶端，並新增可讓系統管理員選擇現有的 Lync 用戶端體驗與新的商務用 Skype 用戶端體驗之間的能力。 如需此更新的相關資訊，請參閱[2015 更新的 Lync 2013 (商務用 Skype)  (KB2889923) ](https://support.microsoft.com/kb/2889923/)。
  
在5月12日的 Office 中2015，會有其他每月更新（包含已更新的商務用 Skype 用戶端）。 許多未套用四月更新的客戶都會收取 Office 2013 的5月更新更新。 本主題中的資訊可協助您準備組織、您的環境，以及用戶端更新的使用者。 若要讓您的使用者與支援小組變得簡單，請使用本主題中的資訊，協助您決定要為使用者執行哪些用戶端體驗，然後在組織中部署用戶端更新之前，先對環境進行變更。
  
- [您要為使用者提供哪些用戶端經驗？](user-experience.md#clientexperience)
    
- [為商務用 Skype 用戶端準備環境](user-experience.md#usinglync)
    
- [協助您準備支援小組和使用者進行更新的資源](user-experience.md#support)
    
> [!NOTE]
> Lync 2013 用戶端體驗不是商務用 Skype 2016 用戶端版本的選項。 在您嘗試設定用戶端環境以使用 Lync 2013 用戶端之前，請檢查用戶端版本，以確保其不是以數位16開頭;例如： x.x.x。 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>您要為使用者提供哪些用戶端經驗？
<a name="clientexperience"> </a>

使用新的商務用 Skype 用戶端，您可以控制使用者可以取得哪些用戶端經驗（包括 Lync 或商務用 Skype）。 預設的用戶端經驗取決於您使用的是 Lync 或商務用 Skype 內部部署或線上。 如果您使用商務用 Skype 線上 (Lync Online) 今天使用 Microsoft 365 Apps 企業版、Microsoft 365 商務標準版或 Office 2013，則更新的商務用 Skype 用戶端體驗（由 Skype 的外觀和感覺所取代）。將會是預設的使用者體驗。 如果您目前使用 Lync Server 內部部署，Lync 用戶端體驗將會是預設值。
  
您可以使用用戶端原則，設定使用者可以取得的用戶端經驗。 用戶端原則是一組設定設定，當使用者登入 Lync 或商務用 Skype 時會套用這些設定。
  
### <a name="skype-for-business-client-experience"></a>商務用 Skype 用戶端體驗

除了 Lync 的所有功能之外，商務用 Skype 還會從 Skype 以簡化的控制項及熟悉的圖示提供新功能。 商務用 Skype 中的某些新功能僅適用于全新商務用 Skype 用戶端體驗。 若要深入瞭解商務用 Skype 中的新功能，請參閱[探索商務用 Skype](https://go.microsoft.com/fwlink/p/?LinkId=528686)。
  
### <a name="lync-client-experience"></a>Lync 用戶端經驗

Lync 用戶端體驗非常類似于您的使用者已熟悉的 Lync 2013 用戶端體驗，但您會想要讓使用者瞭解一些變更。 若要查看 lync 用戶端體驗和 lync 2013 用戶端之間的差異，請參閱為什麼我在[使用 Lync？](https://go.microsoft.com/fwlink/p/?LinkId=544712)和本主題稍後的其他連結時，會看到商務用 Skype。
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>為商務用 Skype 用戶端準備環境
<a name="usinglync"> </a>

您需要做一些工作，才能讓您的環境做好用戶端更新的準備。 在您開始進行任何變更以設定用戶端體驗之前，您必須先確認您使用的商務用 Skype Server 或 Lync Server 版本支援用戶端原則設定。
  
當您確認您使用的商務用 Skype Server 版本或 Lync Server 版本支援原則設定來控制用戶端經驗之後，您必須在環境中設定原則設定。 您需要遵循的特定步驟取決於您所使用的商務用 Skype Server 或 Lync Server 版本，以及您的使用者是否為內部部署或線上。 
  
您會想要在用戶端更新傳遞給您的使用者之前進行這些變更，這樣您就能在第一次啟動商務用 Skype 用戶端時控制用戶端體驗。 下表指向針對使用者所需的用戶端體驗設定環境所需採取的步驟。
  
|**部署**|**商務用 Skype 用戶端體驗**|**Lync 用戶端經驗**|
|:-----|:-----|:-----|
|商務用 Skype Online  <br/> |除了部署用戶端組建 4711.1002 (四月、2015) 或更新版本以外，不需要其他步驟。  <br/> |[線上使用 Lync 用戶端體驗商務用 Skype](user-experience.md#LyncwithSfBO) <br/> |
|商務用 Skype Server 2015  <br/> |除了部署用戶端組建 4711.1002 (四月、2015) 或更新版本以外，不需要其他步驟。  <br/> |[使用 Lync 用戶端經驗與商務用 Skype Server 內部部署](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 和 Lync Server 2010  <br/> |[在 lync server 2013 或 lync server 2010 內部部署中使用 Skype 用戶端體驗](user-experience.md#SkypewithLynconprem) <br/> |[在 lync Server 2013 或 Lync Server 2010 內部部署中使用 Lync 用戶端體驗](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>在 lync server 2013 或 lync server 2010 內部部署中使用 Skype 用戶端體驗
<a name="SkypewithLynconprem"> </a>

如果您想要在內部部署中設定 Skype 用戶端體驗，請遵循本節中的步驟進行。 內部部署的預設體驗
  
 **步驟1：** 首先，請確定您執行的是支援用戶端原則設定的 Lync Server 版本。
  
- **Lync server 2013** -您必須執行 Lync server 2013 的十二月2014累計更新 (5.0.8308.857) 或更新版本。 如需詳細資訊，請參閱 [Lync Server 2013 的更新](https://go.microsoft.com/fwlink/p/?LinkId=532772)。
    
- **Lync server 2010** -您必須執行 Lync server 2010 或更新版本的二月份2015累計更新 (4.0.7577.710) 。 如需詳細資訊，請參閱 [Lync Server 2010 的更新](https://go.microsoft.com/fwlink/p/?LinkId=532771)。
    
  **步驟2：** 接下來，使用用戶端原則，設定商務用 Skype 用戶端的 Skype 用戶端體驗。 使用用戶端原則來設定用戶端經驗的 **選項有三** 個。
  
  **選項1：** 使用全域原則，設定 Skype 用戶端體驗。 請注意，全域原則會套用至您部署中的所有使用者，但是使用者和網站層級原則的優先順序優先于全域原則：
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **選項2：** 修改您在環境中使用的現有用戶端原則，以包含啟用 Skype 用戶端體驗的設定。 這可讓您僅將 Skype 用戶端經驗指派給已指派現有原則的使用者：
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **選項3：** 建立新原則，以指派給使用者，其中包含 Skype 用戶端經驗的設定。 首先，建立新的用戶端原則，並提供原則的名稱做為 **Identity** 參數的值：
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

然後將原則指派給使用者，使用原則名稱 (**Identity** 參數所用的值) 為 **PolicyName** 參數的值：
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **步驟3：** 設定用戶端原則之後，請部署商務用 Skype 用戶端、組建 4711.1002 (四月、2015) 或更新版本。
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>在 lync Server 2013 或 Lync Server 2010 內部部署中使用 Lync 用戶端體驗
<a name="LyncwithLynconprem"> </a>

在內部部署 Lync Server 部署中部署商務用 Skype 用戶端時，這是預設的體驗。 您不需要設定任何用戶端原則使用 Lync 用戶端體驗，但是您可能想要控制用戶端的第一次執行行為。 根據預設，使用者第一次啟動商務用 Skype 用戶端時，會使用 Skype 用戶端體驗，並向使用者顯示通知，要求使用者重新開機用戶端以取得 Lync 用戶端體驗。 您可以設定您的環境，讓使用者第一次啟動用戶端時顯示 Lync 用戶端經驗，以及在用戶端電腦上修改系統登錄以關閉用戶端教學課程。 如需在部署商務用 Skype 用戶端之前所需執行的步驟，請參閱下列其中一個主題：
  
- **lync server 2013**，請參閱 [在 Lync server 2013 中使用商務用 Skype 設定用戶端體驗](/previous-versions/office/lync-server-2013/configure-the-skype-for-business-client-in-lync-server-2013)
    
- **lync server 2010** 請參閱 [在 Lync server 2010 中使用商務用 Skype 設定用戶端體驗](/previous-versions/office/skype-server-2010/dn955209(v=ocs.14))
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>使用 Lync 用戶端經驗與商務用 Skype Server 內部部署
<a name="LyncwithSfBServer"> </a>

如果您想要在內部部署商務用 Skype Server 部署中設定 Lync 用戶端體驗，請遵循本節中的步驟進行。
  
如果您想要在內部部署中設定 Skype 用戶端體驗，請遵循本節中的步驟進行。 內部部署的預設體驗
  
 **步驟1：** 首先，部署商務用 Skype Server。
  
 **步驟2：** 接下來，使用用戶端原則，設定商務用 Skype 用戶端的 Lync 用戶端體驗。 使用用戶端原則來設定用戶端經驗的 **選項有三** 個。
  
 **選項1：** 使用全域原則，設定 Lync 用戶端體驗。 請注意，全域原則會套用至您部署中的所有使用者，但是使用者和網站層級原則的優先順序優先于全域原則：
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **選項2：** 修改您在環境中使用的現有用戶端原則，以包含啟用 Lync 用戶端體驗的設定。 這可讓您僅將 Lync 用戶端經驗指派給已指派現有原則的使用者：
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **選項3：** 建立新原則，將其指派給包括 Lync 用戶端經驗設定的使用者。 首先，建立新的用戶端原則，並提供原則的名稱做為 **Identity** 參數的值：
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

然後將原則指派給使用者，使用原則名稱 (**Identity** 參數所用的值) 為 **PolicyName** 參數的值：
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **步驟3：選擇性**-預設情況下，使用者第一次啟動商務用 Skype 用戶端時，會使用 Skype 用戶端經驗，並向使用者顯示通知，告知使用者是否要重新開機用戶端以取得 Lync 用戶端體驗。 您可以設定環境，讓使用者第一次啟動用戶端時顯示 Lync 用戶端經驗，並在用戶端電腦上修改系統登錄以關閉用戶端教學課程。 如需在部署商務用 Skype 用戶端之前所需執行的步驟，請參閱[Configure the client 體驗 with 商務用 Skype](../../deploy/deploy-clients/configure-the-client-experience.md)。
  
 **步驟4：** 設定用戶端原則之後，請部署商務用 Skype 用戶端、組建 4711.1002 (四月、2015) 或更新版本。
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>線上使用 Lync 用戶端體驗商務用 Skype
<a name="LyncwithSfBO"> </a>

如果您想要設定 Lync 用戶端體驗，並使用商務用 Skype 線上，請遵循本節中的步驟進行。
  
如果您使用商務用 Skype 線上，您仍然可以使用 [遠端 PowerShell] 設定用戶端原則，使用您組織中商務用 Skype 用戶端的 Lync 用戶端體驗。 使用用戶端原則來設定用戶端經驗的 **選項有三** 個。 請注意，原則和參數名稱與您在使用商務用 Skype 或 Lync Server 內部部署時設定用戶端經驗時所用的設定有所不同。
  
 **選項1：** 使用全域原則，設定 Lync 用戶端體驗。 請注意，套用至使用者的用戶端和網站原則將優先于全域原則。
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **選項2：** 修改您在環境中使用的現有用戶端原則，以包含啟用 Lync 用戶端體驗的設定。 這可讓您僅將 Lync 用戶端經驗指派給已指派現有原則的使用者：
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **選項3：** 使用包含 Lync 用戶端經驗設定的自訂原則實例。
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

設定用戶端原則之後，請部署商務用 Skype 用戶端、組建 4711.1002 (四月、2015) 或更新版本。
  
如需如何使用商務用 Skype 線上設定用戶端經驗的詳細資訊，包括如何控制第一個執行經驗的步驟，以及您可以用來設定環境的 PowerShell 腳本，請參閱[在商務用 Skype 與 Lync 用戶端使用者介面之間進行切換](../../../SfbOnline/set-up-skype-for-business-online/switching-the-skype-for-business-and-the-lync-client-user-interfaces.md)。
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>協助您準備支援小組和使用者進行更新的資源
<a name="support"> </a>

為了便於您和您的組織準備好進行轉換，我們有許多其他資源可協助您規劃、教育和接洽使用者。
  
- [影片：介紹商務用 Skype](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [商務用 Skype快速入門手冊 (下載) ](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync 現在已商務用 Skype —請參閱最近更新](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [商務用 Skype：新增使用者的逐步指南](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [為何我在使用 Lync 時看到商務用 Skype？](https://go.microsoft.com/fwlink/p/?LinkID=544712)
