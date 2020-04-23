---
title: 規劃使用者的商務用 Skype 2015 用戶端體驗
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: 摘要：瞭解新的商務用 Skype 和您可以採取的步驟，以準備您的環境和使用者進行更新，不論您使用的是商務用 Skype Online、商務用 skype Server 2019、商務用 skype Server 2015、Lync Server 2013 或 Lync Server 2010。
ms.openlocfilehash: c1fecbdb5a4ec0a19e464a57ee128d2d00ad501f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777748"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>規劃使用者的商務用 Skype 2015 用戶端體驗
 
**摘要：** 瞭解新的商務用 Skype 和您可以採取的步驟，以準備您的環境和使用者進行更新，不論您使用的是商務用 Skype Online、商務用 skype Server 2019、商務用 skype Server 2015、Lync Server 2013 或 Lync Server 2010。
  
Lync 2013 的2015年4月14日更新包含新的商務用 Skype 使用者介面。 此項更新可讓系統管理員控制用戶端的外觀與風格，並選擇要保留 Lync 2013 用戶端經驗，還是使用已改善的商務用 Skype 用戶端體驗。 商務用 Skype 用戶端會有效取代 Lync 2013 用戶端，並新增可讓系統管理員在現有的 Lync 用戶端體驗與新的商務用 Skype 用戶端體驗之間選擇的能力。 如需此更新的詳細資訊，請參閱[Lync 2013 （商務用 Skype）的2015更新（KB2889923）](https://support.microsoft.com/kb/2889923/)。
  
在5月12日，2015會從 Office 更新其他每月更新，包括已更新的商務用 Skype 用戶端。 許多未套用四月更新的客戶都會收取 Office 2013 的5月更新版更新。 本主題中的資訊可協助您準備組織、您的環境，以及用戶端更新的使用者。 若要讓您的使用者與支援小組變得簡單，請使用本主題中的資訊，協助您決定要為使用者執行哪些用戶端體驗，然後在組織中部署用戶端更新之前，先對環境進行變更。
  
- [您要為使用者提供哪些用戶端經驗？](user-experience.md#clientexperience)
    
- [為商務用 Skype 用戶端準備您的環境](user-experience.md#usinglync)
    
- [協助您準備支援小組和使用者進行更新的資源](user-experience.md#support)
    
> [!NOTE]
> Lync 2013 用戶端體驗不是商務用 Skype 2016 用戶端版本的選項。 在您嘗試設定用戶端環境以使用 Lync 2013 用戶端之前，請檢查用戶端版本，以確保其不是以數位16開頭;例如： x.x.x。 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>您要為使用者提供哪些用戶端經驗？
<a name="clientexperience"> </a>

透過新的商務用 Skype 用戶端，您可以控制使用者可以取得哪些用戶端經驗（即 Lync 或商務用 Skype）。 預設的用戶端經驗取決於您使用的是 Lync 或商務用 Skype 內部部署或線上。 如果您目前使用商務用 Skype Online （Lync Online）和 Microsoft 365 應用程式的企業版、Microsoft 365 Business Standard 或 Office 2013，已更新的商務用 Skype 用戶端體驗（透過 Skype 的外觀與風格）將是預設的使用者體驗。 如果您目前使用 Lync Server 內部部署，Lync 用戶端體驗將會是預設值。
  
您可以使用用戶端原則，設定使用者可以取得的用戶端經驗。 用戶端原則是在使用者登入 Lync 或商務用 Skype 時，套用至使用者的一組設定設定。
  
### <a name="skype-for-business-client-experience"></a>商務用 Skype 用戶端體驗

除了 Lync 的所有功能之外，商務用 Skype 還會透過 Skype 的簡化控制項和常見圖示來提供新功能。 商務用 Skype 中的一些新功能僅適用于新的商務用 Skype 用戶端體驗。 若要深入瞭解商務用 Skype 中的新功能，請參閱[探索商務用 skype](https://go.microsoft.com/fwlink/p/?LinkId=528686)。
  
### <a name="lync-client-experience"></a>Lync 用戶端經驗

Lync 用戶端體驗非常類似于您的使用者已熟悉的 Lync 2013 用戶端體驗，但您會想要讓使用者瞭解一些變更。 若要查看 Lync 用戶端體驗和 Lync 2013 用戶端之間的差異，請參閱為何我在[使用 Lync 時看到商務用 Skype？](https://go.microsoft.com/fwlink/p/?LinkId=544712)和本主題稍後的其他連結。
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>為商務用 Skype 用戶端準備您的環境
<a name="usinglync"> </a>

您需要做一些工作，才能讓您的環境做好用戶端更新的準備。 在您開始進行任何變更以設定用戶端體驗之前，您必須先確定您使用的是商務用 Skype Server 或 Lync Server 版本（支援用戶端原則設定）。
  
在您確認您使用的商務用 Skype Server 或 Lync Server 版本支援原則設定以控制用戶端經驗之後，您必須在環境中設定原則設定。 您需要遵循的特定步驟取決於您所使用的商務用 Skype Server 或 Lync Server 版本，以及您的使用者是否為內部部署或線上。 
  
您將會想要在用戶端更新傳遞給您的使用者之前進行這些變更，這樣您就能在第一次啟動商務用 Skype 用戶端時，控制用戶端的體驗。 下表指向針對使用者所需的用戶端體驗設定環境所需採取的步驟。
  
|**部署**|**商務用 Skype 用戶端體驗**|**Lync 用戶端經驗**|
|:-----|:-----|:-----|
|商務用 Skype Online  <br/> |除了部署用戶端組建4711.1002 （四月、2015）或更新版本以外，不需要其他步驟。  <br/> |[使用 Lync 用戶端與商務用 Skype Online 的經驗](user-experience.md#LyncwithSfBO) <br/> |
|商務用 Skype Server 2015  <br/> |除了部署用戶端組建4711.1002 （四月、2015）或更新版本以外，不需要其他步驟。  <br/> |[使用 Lync 用戶端與商務用 Skype Server 內部部署的經驗](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 和 Lync Server 2010  <br/> |[在 Lync Server 2013 或 Lync Server 2010 內部部署中使用 Skype 用戶端體驗](user-experience.md#SkypewithLynconprem) <br/> |[在 lync Server 2013 或 Lync Server 2010 內部部署中使用 Lync 用戶端體驗](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>在 Lync Server 2013 或 Lync Server 2010 內部部署中使用 Skype 用戶端體驗
<a name="SkypewithLynconprem"> </a>

如果您想要在內部部署中設定 Skype 用戶端體驗，請遵循本節中的步驟進行。 內部部署的預設體驗
  
 **步驟1：** 首先，請確定您執行的是支援用戶端原則設定的 Lync Server 版本。
  
- **Lync server 2013** -您必須執行 Lync server 2013 或更新版本的十二月2014累計更新（5.0.8308.857）。 如需詳細資訊，請參閱[Lync Server 2013 的更新](https://go.microsoft.com/fwlink/p/?LinkId=532772)。
    
- **Lync server 2010** -您必須執行 Lync server 2010 或更新版本的二月份2015累積更新（4.0.7577.710）。 如需詳細資訊，請參閱[Lync Server 2010 的更新](https://go.microsoft.com/fwlink/p/?LinkId=532771)。
    
  **步驟2：** 接下來，使用用戶端原則，設定商務用 Skype 用戶端的 Skype 用戶端經驗。 使用用戶端原則來設定用戶端經驗的**選項有三**個。
  
  **選項1：** 使用全域原則，設定 Skype 用戶端體驗。 請注意，全域原則會套用至您部署中的所有使用者，但是使用者和網站層級原則的優先順序優先于全域原則：
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **選項2：** 修改您在環境中使用的現有用戶端原則，以包含啟用 Skype 用戶端經驗的設定。 這可讓您僅將 Skype 用戶端經驗指派給已指派現有原則的使用者：
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **選項3：** 建立新原則，將其指派給包含 Skype 用戶端經驗設定的使用者。 首先，建立新的用戶端原則，並提供原則的名稱做為**Identity**參數的值：
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

然後將原則指派給使用者，並使用原則的名稱（身分**識別**參數所用的值）做為**PolicyName**參數的值：
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **步驟3：** 設定用戶端原則之後，請部署商務用 Skype 用戶端、組建4711.1002 （四月、2015）或更新版本。
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>在 lync Server 2013 或 Lync Server 2010 內部部署中使用 Lync 用戶端體驗
<a name="LyncwithLynconprem"> </a>

當商務用 Skype 用戶端部署在內部部署 Lync Server 部署中時，這是預設的體驗。 您不需要設定任何用戶端原則使用 Lync 用戶端體驗，但是您可能想要控制用戶端的第一次執行行為。 根據預設，使用者第一次啟動商務用 Skype 用戶端時，會使用 Skype 用戶端經驗，並向使用者顯示通知，要求他們重新開機用戶端以取得 Lync 用戶端體驗。 您可以設定您的環境，讓使用者第一次啟動用戶端時顯示 Lync 用戶端經驗，以及在用戶端電腦上修改系統登錄以關閉用戶端教學課程。 如需在部署商務用 Skype 用戶端之前所需執行的步驟，請參閱下列其中一個主題：
  
- **Lync server 2013**，請參閱[Configure Client experience With 商務用 Skype in Lync server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532732)
    
- **Lync server 2010**請參閱[Configure Client experience With 商務用 Skype in Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532733)
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>使用 Lync 用戶端與商務用 Skype Server 內部部署的經驗
<a name="LyncwithSfBServer"> </a>

如果您想要在內部部署商務用 Skype Server 部署中設定 Lync 用戶端體驗，請遵循本節中的步驟進行。
  
如果您想要在內部部署中設定 Skype 用戶端體驗，請遵循本節中的步驟進行。 內部部署的預設體驗
  
 **步驟1：** 首先，部署商務用 Skype Server。
  
 **步驟2：** 接下來，使用用戶端原則，設定商務用 Skype 用戶端的 Lync 用戶端體驗。 使用用戶端原則來設定用戶端經驗的**選項有三**個。
  
 **選項1：** 使用全域原則，設定 Lync 用戶端體驗。 請注意，全域原則會套用至您部署中的所有使用者，但是使用者和網站層級原則的優先順序優先于全域原則：
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **選項2：** 修改您在環境中使用的現有用戶端原則，以包含啟用 Lync 用戶端體驗的設定。 這可讓您僅將 Lync 用戶端經驗指派給已指派現有原則的使用者：
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **選項3：** 建立新原則，將其指派給包括 Lync 用戶端經驗設定的使用者。 首先，建立新的用戶端原則，並提供原則的名稱做為**Identity**參數的值：
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

然後將原則指派給使用者，並使用原則的名稱（身分**識別**參數所用的值）做為**PolicyName**參數的值：
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **步驟3：選用**預設值，使用者第一次啟動商務用 skype 用戶端時，會使用 skype 用戶端經驗，並向使用者顯示通知，告知使用者是否要重新開機用戶端以取得 Lync 用戶端體驗。 您可以設定環境，讓使用者第一次啟動用戶端時顯示 Lync 用戶端經驗，並在用戶端電腦上修改系統登錄以關閉用戶端教學課程。 如需在部署商務用 Skype 用戶端之前所需執行的步驟，請參閱[Configure the 用戶端經驗 with The 商務用 skype](../../deploy/deploy-clients/configure-the-client-experience.md)。
  
 **步驟4：** 設定用戶端原則之後，請部署商務用 Skype 用戶端、組建4711.1002 （四月、2015）或更新版本。
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>使用 Lync 用戶端與商務用 Skype Online 的經驗
<a name="LyncwithSfBO"> </a>

如果您想要設定 Lync 用戶端體驗，並使用商務用 Skype Online，請遵循本節中的步驟進行。
  
如果您使用的是商務用 Skype Online，您仍然可以使用遠端 PowerShell 設定用戶端原則，在組織中使用商務用 Skype 用戶端的 Lync 用戶端經驗。 使用用戶端原則來設定用戶端經驗的**選項有三**個。 請注意，原則及參數名稱與您在使用商務用 Skype 或 Lync Server 內部部署時，用來設定用戶端體驗的設定不同。
  
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

設定用戶端原則之後，請部署商務用 Skype 用戶端、組建4711.1002 （四月、2015）或更新版本。
  
如需如何使用商務用 Skype Online 設定用戶端經驗的詳細資訊，包括如何控制第一個執行經驗的步驟，以及可用來設定環境的 PowerShell 腳本，請參閱[在商務用 skype 和 Lync 用戶端使用者介面之間切換](https://aka.ms/SfBOUI)。
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>協助您準備支援小組和使用者進行更新的資源
<a name="support"> </a>

為了便於您和您的組織準備好進行轉換，我們有許多其他資源可協助您規劃、教育和接洽使用者。
  
- [影片：介紹商務用 Skype](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [商務用 Skype 快速入門手冊（下載）](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync 現在是商務用 Skype，請參閱最近更新](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [商務用 Skype：新使用者的逐步指南](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [為何我在使用 Lync 時看到商務用 Skype？](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

