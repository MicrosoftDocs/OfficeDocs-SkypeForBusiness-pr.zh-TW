---
title: 為您的使用者規劃商務用 Skype 2015 用戶端體驗
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: 摘要：瞭解新的商務用 Skype，以及您可以採取哪些步驟來準備您的環境及使用者進行更新，不論您使用的是商務用 Skype Online、商務用 skype Server 2019、商務用 Skype server 2015、Lync Server 2013，還是Lync Server 2010。
ms.openlocfilehash: 21a28af999b285910884241e6e7809a88b943a87
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989848"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a>為您的使用者規劃商務用 Skype 2015 用戶端體驗
 
**摘要：** 無論您使用的是商務用 Skype Online、商務用 skype Server 2019、商務用 skype server 2015、Lync Server 2013 或 Lync Server 2010，您都可以在新的商務用 Skype 和使用者進行更新時採取這些步驟來準備您的環境及使用者。
  
Lync 2013 的2015年4月14日（含新的商務用 Skype 使用者介面）。 此更新可讓系統管理員控制用戶端的外觀與風格，並選擇是否要保留 Lync 2013 用戶端體驗，或使用改良的商務用 Skype 用戶端體驗。 商務用 Skype 用戶端能有效地取代 Lync 2013 用戶端，並新增了管理員在現有的 Lync 用戶端體驗與新的商務用 Skype 用戶端體驗之間進行選擇的能力。 如需此更新的相關資訊，請參閱[Lync 2013 的2015（商務用 Skype）更新（KB2889923）](https://support.microsoft.com/en-us/kb/2889923/)。
  
在5月12日，您將會有來自 Office 的其他每月更新2015，包括更新的商務用 Skype 用戶端。 許多未套用4月更新的客戶將會挑選 Office 2013 的5月12日更新。 本主題中的資訊將協助您準備貴組織、您的環境及使用者，以進行用戶端更新。 若要讓您的使用者和支援小組輕鬆進行過渡，請使用本主題中的資訊，協助您決定您想要的使用者用戶端體驗，然後在您的組織中部署用戶端更新之前，對您的環境進行變更。
  
- [您想要為使用者提供哪些用戶端體驗？](user-experience.md#clientexperience)
    
- [為商務用 Skype 用戶端準備您的環境](user-experience.md#usinglync)
    
- [協助您準備支援小組與您的最終使用者以進行更新的資源](user-experience.md#support)
    
> [!NOTE]
> Lync 2013 用戶端體驗不是商務用 Skype 2016 用戶端版本的選項。 在您嘗試將用戶端環境設定為使用 Lync 2013 用戶端之前，請先檢查用戶端版本，以確保它不是以數位16開頭;例如： x.x.x。 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a>您想要為使用者提供哪些用戶端體驗？
<a name="clientexperience"> </a>

使用新的商務用 Skype 用戶端，您可以控制使用者取得的用戶端體驗（無論是 Lync 或商務用 Skype）。 預設的用戶端體驗取決於您使用的是 Lync 或商務用 Skype 內部部署或線上。 如果您目前使用的是商務用 Skype Online （Lync Online）與 Office 365 專業增強版、Office 365 Business Premium 或 Office 2013，更新的商務用 Skype 用戶端體驗（由 Skype 的外觀和風格來激發）就是預設的使用者體驗。 如果您目前使用的是 Lync Server 內部部署，Lync 用戶端體驗將會是預設值。
  
您可以使用用戶端原則設定使用者取得的用戶端體驗。 用戶端原則是一組設定，當使用者登入 Lync 或商務用 Skype 時，就會套用這些設定。
  
### <a name="skype-for-business-client-experience"></a>商務用 Skype 用戶端體驗

除了 Lync 的所有功能之外，商務用 Skype 還能透過簡化的控制項和 Skype 中常見的圖示來提供新功能。 商務用 Skype 中的一些新功能僅適用于新的商務用 Skype 用戶端體驗。 若要深入瞭解商務用 Skype 中的新功能，請參閱[探索商務用 skype](https://go.microsoft.com/fwlink/p/?LinkId=528686)。
  
### <a name="lync-client-experience"></a>Lync 用戶端體驗

Lync 用戶端體驗與您的使用者已經熟悉的 Lync 2013 用戶端體驗非常類似，但是您需要讓使用者知道一些變更。 若要查看 Lync 用戶端體驗與 Lync 2013 用戶端之間的不同之處，請參閱為什麼我在[使用 Lync 時，我會看到商務用 Skype？](https://go.microsoft.com/fwlink/p/?LinkId=544712)以及本主題稍後的其他連結。
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a>為商務用 Skype 用戶端準備您的環境
<a name="usinglync"> </a>

您必須執行一些動作，才能讓您的環境準備好進行用戶端更新。 開始進行任何變更以設定用戶端體驗之前，您必須先確認您使用的是商務用 Skype Server 或支援用戶端原則設定的 Lync 伺服器版本。
  
一旦您確認您使用的是支援原則設定以控制用戶端體驗的商務用 Skype Server 或 Lync Server 版本，就必須在您的環境中設定原則設定。 您需要追蹤的特定步驟取決於您所使用的商務用 Skype Server 或 Lync Server 版本，以及您的使用者是否為內部部署或線上。 
  
您可能會想要在用戶端更新傳送給您的使用者之前進行這些變更，好讓您在第一次啟動商務用 Skype 用戶端時控制用戶端體驗。 下清單格會指出針對您的使用者所需的用戶端體驗設定您的環境所需採取的步驟。
  
|**Deployment**|**商務用 Skype 用戶端體驗**|**Lync 用戶端體驗**|
|:-----|:-----|:-----|
|商務用 Skype Online  <br/> |部署用戶端組建4711.1002 （4月、2015）或更新版本之外，不需其他其他步驟。  <br/> |[在商務用 Skype Online 中使用 Lync 用戶端體驗](user-experience.md#LyncwithSfBO) <br/> |
|商務用 Skype Server 2015  <br/> |部署用戶端組建4711.1002 （4月、2015）或更新版本之外，不需其他其他步驟。  <br/> |[在內部部署使用商務用 Skype Server 的 Lync 用戶端體驗](user-experience.md#LyncwithSfBServer) <br/> |
|Lync Server 2013 和 Lync Server 2010  <br/> |[在內部部署中使用 Lync Server 2013 或 Lync Server 2010 的 Skype 用戶端體驗](user-experience.md#SkypewithLynconprem) <br/> |[在部署中使用 lync Server 2013 或 Lync Server 2010 的 Lync 用戶端體驗](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>在內部部署中使用 Lync Server 2013 或 Lync Server 2010 的 Skype 用戶端體驗
<a name="SkypewithLynconprem"> </a>

如果您想要設定內部部署中的 Skype 用戶端體驗，請遵循本節中的步驟操作。 內部部署的預設體驗
  
 **步驟1：** 首先，請確定您執行的是支援用戶端原則設定的 Lync Server 版本。
  
- **Lync server 2013** -您必須執行 lync server 2013 或更新版本的2014年12月累計更新（5.0.8308.857）。 如需詳細資訊，請參閱[Lync Server 2013 更新](https://go.microsoft.com/fwlink/p/?LinkId=532772)。
    
- **Lync server 2010** -您必須執行 lync server 2010 或更新版本的2月2015累計更新（4.0.7577.710）。 如需詳細資訊，請參閱[Lync Server 2010 更新](https://go.microsoft.com/fwlink/p/?LinkId=532771)。
    
  **步驟2：** 接著，使用用戶端原則來設定商務用 Skype 用戶端的 Skype 用戶端體驗。 有**3 個選項**可讓您使用用戶端原則來設定用戶端體驗。
  
  **選項1：** 使用全域原則設定 Skype 用戶端體驗。 請注意，全域原則會套用到您部署中的所有使用者，但使用者和網站層級原則的優先順序高於全域原則：
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 **選項2：** 修改您在您的環境中使用的現有用戶端原則，以包含啟用 Skype 用戶端體驗的設定。 這可讓您僅將 Skype 用戶端體驗指派給已指派現有原則的使用者：
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 **選項3：** 建立新原則，指派給包括 Skype 用戶端體驗設定的使用者。 首先，建立新的用戶端原則，並提供原則的名稱做為身分**識別**參數的值：
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

然後，將原則指派給使用者，使用原則的名稱（您用於身分**識別**參數的值）做為**PolicyName**參數的值：
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 **步驟3：** 在您設定用戶端原則之後，請部署商務用 Skype 用戶端、組建4711.1002 （四月、2015）或更新版本。
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a>在部署中使用 lync Server 2013 或 Lync Server 2010 的 Lync 用戶端體驗
<a name="LyncwithLynconprem"> </a>

這是商務用 Skype 用戶端部署在內部部署 Lync Server 部署中的預設體驗。 您不需要將任何用戶端原則設定為使用 Lync 用戶端體驗，但您可能會想要控制用戶端的第一次執行行為。 根據預設，使用者第一次啟動商務用 Skype 用戶端時，會使用 Skype 用戶端體驗，並向使用者顯示通知，要求他們重新開機用戶端以取得 Lync 用戶端體驗。 您可以設定您的環境，讓使用者第一次啟動用戶端時顯示 Lync 用戶端的體驗，以及在用戶端電腦上修改系統登錄，以關閉用戶端教學課程。 如需在部署商務用 Skype 用戶端之前所需執行的步驟，請參閱下列其中一個主題：
  
- **Lync server 2013**，請參閱[在 Lync Server 2013 中設定商務用 Skype 的用戶端體驗](https://go.microsoft.com/fwlink/p/?LinkId=532732)
    
- **Lync server 2010**請參閱[在 Lync Server 2010 中設定商務用 Skype 的用戶端體驗](https://go.microsoft.com/fwlink/p/?LinkId=532733)
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a>在內部部署使用商務用 Skype Server 的 Lync 用戶端體驗
<a name="LyncwithSfBServer"> </a>

如果您想要在內部部署商務用 Skype Server 部署中設定 Lync 用戶端體驗，請遵循本節中的步驟。
  
如果您想要設定內部部署中的 Skype 用戶端體驗，請遵循本節中的步驟操作。 內部部署的預設體驗
  
 **步驟1：** 首先，請部署商務用 Skype 伺服器。
  
 **步驟2：** 接著，使用用戶端原則，以商務用 Skype 用戶端來設定 Lync 用戶端體驗。 有**3 個選項**可讓您使用用戶端原則來設定用戶端體驗。
  
 **選項1：** 使用全域原則設定 Lync 用戶端體驗。 請注意，全域原則會套用到您部署中的所有使用者，但使用者和網站層級原則的優先順序高於全域原則：
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 **選項2：** 修改您在您的環境中使用的現有用戶端原則，以包含啟用 Lync 用戶端體驗的設定。 這可讓您僅將 Lync 用戶端體驗指派給已指派現有原則的使用者：
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 **選項3：** 建立新原則，指派給包括 Lync 用戶端體驗設定的使用者。 首先，建立新的用戶端原則，並提供原則的名稱做為身分**識別**參數的值：
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

然後，將原則指派給使用者，使用原則的名稱（您用於身分**識別**參數的值）做為**PolicyName**參數的值：
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 **步驟3：選用**預設，使用者第一次啟動商務用 skype 用戶端時，會使用 skype 用戶端體驗，並向使用者顯示通知，要求他們重新開機用戶端以取得 Lync 用戶端體驗。 您可以設定您的環境，讓使用者第一次啟動用戶端，以及關閉用戶端教學課程，只要修改用戶端電腦上的 system registry，就能顯示 Lync 用戶端教學課程。 如需在部署商務用 Skype 用戶端之前所需執行的步驟，請參閱[使用商務用 Skype 設定用戶端體驗](../../deploy/deploy-clients/configure-the-client-experience.md)。
  
 **步驟4：** 在您設定用戶端原則之後，請部署商務用 Skype 用戶端、組建4711.1002 （四月、2015）或更新版本。
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a>在商務用 Skype Online 中使用 Lync 用戶端體驗
<a name="LyncwithSfBO"> </a>

如果您想要設定 Lync 用戶端體驗，並使用商務用 Skype Online，請遵循本節中的步驟進行。
  
如果您使用的是商務用 Skype Online，您仍然可以使用遠端 PowerShell 來設定用戶端原則，在您組織中的商務用 Skype 用戶端上使用 Lync 用戶端體驗。 有**3 個選項**可讓您使用用戶端原則來設定用戶端體驗。 請注意，原則與參數名稱與您在使用商務用 Skype 或 Lync Server 內部部署時設定的用戶端體驗有所不同。
  
 **選項1：** 使用全域原則設定 Lync 用戶端體驗。 請注意，套用至使用者的用戶端和網站原則將會優先于全域原則。
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **選項2：** 修改您在您的環境中使用的現有用戶端原則，以包含啟用 Lync 用戶端體驗的設定。 這可讓您僅將 Lync 用戶端體驗指派給已指派現有原則的使用者：
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 **選項3：** 使用包括 Lync 用戶端體驗設定的自訂原則實例。
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

在您設定用戶端原則之後，請部署商務用 Skype 用戶端、組建4711.1002 （四月、2015）或更新版本。
  
如需如何在商務用 Skype Online 中設定用戶端體驗的詳細資訊，包括如何控制您可以用來設定您的環境的第一次執行體驗和 PowerShell 腳本，請參閱[在商務用 skype 和 Lync 用戶端使用者介面之間切換](https://aka.ms/SfBOUI)。
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a>協助您準備支援小組與您的最終使用者以進行更新的資源
<a name="support"> </a>

為了讓您和您的組織更輕鬆地進行轉場作業，我們有許多其他資源可協助您規劃、教育與接洽最終使用者。
  
- [影片：介紹商務用 Skype](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [商務用 Skype 快速入門手冊（下載）](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [Lync 現在是商務用 Skype-查看新功能](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [商務用 Skype：適用于新使用者的逐步指南](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [為什麼當我使用 Lync 時，我會看到商務用 Skype？](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

