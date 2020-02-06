---
title: 現代驗證支援的商務用 Skype 拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: 本文列出商務用 Skype 中的新式驗證支援哪些線上和內部部署拓撲，以及適用于每個拓朴的安全性功能。
ms.openlocfilehash: 2eb043768c46406696b32da5dfb84e2358a30749
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815821"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>現代驗證支援的商務用 Skype 拓撲
 
本文列出商務用 Skype 中的新式驗證支援哪些線上和內部部署拓撲，以及適用于每個拓朴的安全性功能。
  
## <a name="modern-authentication-in-skype-for-business"></a>商務用 Skype 中的新式驗證

商務用 Skype 可以利用新式驗證的安全性優勢。 因為商務用 Skype 與 Exchange 密切搭配使用，所以商務用 Skype 用戶端使用者將會看到 Exchange 的 MA 狀態也會受到影響。 如果您有商務用 Skype 剝離-網域混合，這也適用。 這是許多移動元件，但這裡的目標就是支援拓撲的簡單視覺化清單。
  
在已知商務用 Skype、商務用 Skype online、Exchange Server 和 Exchange online 中，MA 支援哪些拓朴？
  
<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. --> 
  
### <a name="supported-ma-topologies-in-skype-for-business"></a>商務用 Skype 中支援的 MA 拓撲

有可能有兩個伺服器應用程式，以及兩個 Office 365 工作負載，與 MA 使用的商務用 Skype 拓朴有關。
  
- 商務用 Skype server （CU 5）內部部署
    
- 商務用 Skype online （SFBO）
    
- Exchange server 內部部署
    
- Exchange server online （EXO）
    
MA 的另一個重要部分是瞭解使用者將在哪裡進行驗證（authN）和授權（authZ）。 這兩個選項如下所示：
  
- Microsoft 雲端中的 Azure AD、online
    
- Active Directory 同盟伺服器（ADFS）內部部署
    
如此一來，看起來就像這樣，在雲端中使用 EXO 和 SFBO 與 Azure AD，以及 Exchange Server （EXCH）及商務用 Skype server （SFB）-內部部署。
  
![所有應用程式（Exchange 和商務用 Skype）與工作負荷（EXO 和 SFBO）的範例，以及開啟 MA 時可參與的授權伺服器（ADFS 和 evoSTS）。](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)
  
以下是支援的拓撲。 請記住圖形的索引鍵：
  
- 如果圖示呈灰色或灰色，就不會用於場景中。
    
- EXO 是 Exchange Online。
    
- SFBO 是商務用 Skype Online。
    
- EXCH 是 Exchange 內部部署。
    
- SFB 是商務用 Skype 內部部署。
    
- 授權伺服器是由三角形表示，例如，Azure AD 是一個三角形，其中有一個雲端。
    
- 當用戶端嘗試到達指定的伺服器資源時，會使用的箭頭指向授權伺服器。
    
首先，讓我們在內部部署或僅限雲端拓撲中使用商務用 Skype 來涵蓋 MA。
  
> [!IMPORTANT]
> 您準備好在商務用 Skype Online 中設定新式驗證嗎？ 啟用此功能的步驟在[這裡](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。 
  
|拓朴名稱  <br/> |範例  <br/> |說明  <br/> |受  <br/> |
|:-----|:-----|:-----|:-----|
|僅限雲端  <br/> |![支援的 SFB，含 MA 拓撲，僅限雲端。](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)使用者駐留/信箱位於：線上  <br/> |EXO 和 SFBO 的 MA 都是開啟的。  <br/> 因此，授權伺服器是 Azure AD。  <br/> |多重要素驗證（MFA）、以用戶端憑證為基礎的驗證（CBA）、條件式存取（CA）/Mobile 應用程式管理（MAM）與 Intune。 \*  <br/> |
|僅限內部部署  <br/> |![支援的 SFB 只有 MA 拓朴，且僅限內部部署。](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)使用者駐留/信箱位於：內部部署  <br/> |MA 是針對 SFB 內部部署所開啟。  <br/> 因此，授權伺服器是 ADFS。  <br/> 如需設定詳細資料，請參閱[這篇文章。](https://technet.microsoft.com/en-us/library/mt710548.aspx) <br/> |MFA （僅限 Windows 桌上出版-不支援行動用戶端）。 沒有 Exchange 整合功能。  <br/><p> **我們不建議採用這種方法。請參閱這裡：**[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)<p/> |
   
> [!IMPORTANT]
> 建議您在商務用 Skype 和 Exchange （及其線上等）中，MA 狀態都是相同的，以減少提示數量。 
  
混合式拓朴涉及 SFB 分割網域混合式的組合。 以下是目前支援的混合拓撲：
  
|拓朴名稱  <br/> |範例  <br/> |說明  <br/> |受  <br/> |
|:-----|:-----|:-----|:-----|
|混合式1  <br/> |![支援的 SFB，含 MA 拓撲，混合式1（EXO + SFB）。](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> 使用者駐留/信箱位於： EXO 和 SFB  <br/> |SFB 沒有啟用 MA;此拓朴中不提供 SFB MA 功能。  <br/> |沒有 SFB 的 MA 功能。  <br/> |
|混合式2  <br/> |![支援的 MA 與 S4B 混合式拓朴2、SFBO 加 MA，使用 EXCH 內部部署。](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> 使用者駐留/信箱位於： EXCH 和 SFBO  <br/> |MA 僅適用于 SFBO。 授權伺服器是駐留在 SFBO 的使用者的 Azure AD，但 EXCH 內部部署的 AD。  <br/> |使用 Intune 進行 MFA、CBA、CA/MAM。\*  <br/> |
|混合3  <br/> |![支援的 MA 與 SFB、EXO [MA 開啟]，加上 EXCH 和 SFB 內部部署。](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> 使用者駐留/信箱位於： EXO + SFB 或 EXCH + SFB  <br/> |此拓朴中不提供 SFB MA 功能  <br/> |沒有 SFB 的 MA 功能。  <br/> |
|混合式4  <br/> |![支援的 MA 與 SFB、SFBO [MA 開啟]，加上 EXCH 和 SFB。](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> 使用者駐留/信箱位於： EXCH + SFBO 或 EXCH + SFB  <br/> |MA 是針對 SFBO，因此授權伺服器是駐留在 SFBO 中的使用者的 Azure AD。 內部部署 SFB 和 EXO 中的使用者使用 AD。  <br/> |僅供線上使用者使用 Intune 的 MFA、CBA、CA/MAM。\*  <br/> |
|混合5  <br/> |![SFB、EXO 和 MA 支援的 MA，以及 EXCH 和 SFB 在內部部署的 SFBO。](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> 使用者駐留/信箱位於： EXO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB  <br/> |MA 都在 EXO 和 SFBO 中，因此授權伺服器是駐留在 SFBO 中的使用者的 Azure AD;內部部署 EXCH 和 SFB 中的使用者使用 AD。  <br/> |僅供線上使用者使用 Intune 的 MFA、CBA、CA/MAM。\*  <br/> |
|混合式6  <br/> |![在混合式6拓朴中，現代驗證是在所有四個 possibile 位置中，即適用于新式驗證的理想 situtation。](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> 使用者駐留/信箱位於： EXO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB  <br/> |MA 是位於任何地方，因此授權伺服器是適用于所有使用者的 Azure AD。 （線上及內部部署）  <br/>  如需[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)部署步驟，請參閱。 <br/> |針對所有使用者進行 MFA、CBA 和 CA/MAM （透過 Intune）。  <br/> |
   
\*-MFA 包括 Windows Desktop、MAC、iOS、Android 裝置和 Windows phone;CBA 包括 Windows Desktop、iOS 和 Android 裝置;含 Intune 的 CA/MAM，包括 Android 和 iOS 裝置。 
  
> [!IMPORTANT]
> 很重要的一點是，在某些情況下，使用者可能會看到**多個提示**，特別是在用戶端可能需要並要求的所有伺服器資源中，MA 狀態不是相同的，這種情況與所有混合式拓朴版本一樣。

> [!IMPORTANT]
> 另請注意，在某些情況下（混合使用1、3和5），必須設定[AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/en-us/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online)登錄機碼，才能正確地設定 Windows 桌面用戶端。
  

