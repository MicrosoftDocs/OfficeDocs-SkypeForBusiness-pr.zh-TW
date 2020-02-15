---
title: 商務用 Skype 的新式驗證與支援的商務拓撲
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
description: 本文列出什麼線上和內部部署的拓撲支援商務，以及套用至每種拓撲的安全性功能中用 Skype 的新式驗證。
ms.openlocfilehash: b23c2081833b43f0f734febc0b18356abf63506e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043755"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>商務用 Skype 的新式驗證與支援的商務拓撲
 
本文列出什麼線上和內部部署的拓撲支援商務，以及套用至每種拓撲的安全性功能中用 Skype 的新式驗證。
  
## <a name="modern-authentication-in-skype-for-business"></a>商務用 skype 的新式驗證

商務用 Skype 可以利用新式驗證安全性的優點。 因為 Skype for Business works 密切與 Exchange、 商務用戶端使用者登入行為 Skype 會看到將也會受到 Exchange MA 狀態。 如果您有分割網域混合式商務用 Skype 時，這也會套用。 這是許多部分，但其目的是容易視覺化支援的拓撲的清單。
  
指定 Skype 用於企業、 商務用 Skype、 Exchange Server 和 Exchange online，與 MA 支援何種拓撲？
  
<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. --> 
  
### <a name="supported-ma-topologies-in-skype-for-business"></a>商務用 Skype 中支援的 MA 拓撲

可能有兩個伺服器應用程式，以及兩個 Office 365 工作負載，涉及與 Skype MA 所使用的商務拓撲。
  
- Skype 商務伺服器 (CU 5) 內部部署
    
- Skype 商務 online (SFBO)
    
- Exchange server 內部部署
    
- Exchange 伺服器在線上 (EXO)
    
另一個重要部分 MA 會知道 (authN) 的驗證和授權 (authZ) 的使用者將會發生。 兩個選項如下：
  
- Azure AD，線上 Microsoft Cloud 中
    
- Active Directory 同盟伺服器 (ADFS) 內部部署
    
讓它看起來有點像這樣，EXO 與 SFBO 與 Azure AD，在雲端中的 Exchange 伺服器 (NM-EXCH-UM-1ST) 與 Skype for Business server (SFB) 上-prem.
  
![（Exchange 和商務用 Skype） 的所有應用程式和工作負載 （EXO 和 SFBO），及兩個時開啟 MA 可以涉及的授權伺服器 （ADFS 與 evoSTS） 的範例。](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)
  
以下是支援的拓撲。 請注意圖形的機碼：
  
- 如果圖示會變暗，或暗，它是不適用於此案例。
    
- EXO 是 Exchange Online。
    
- SFBO 是商務用 Skype。
    
- NM-EXCH-UM-1ST 是 Exchange 內部部署。
    
- SFB 是 Skype 商務內部部署。
    
- 授權伺服器由三角形表示，例如，Azure AD 具有其後面雲端的三角形。
    
- 箭號指向用戶端嘗試連線到指定的伺服器資源時，所使用的授權伺服器。
    
第一筆、 讓我們涵蓋 MA 與同時在內部部署-僅限，或僅限雲端拓樸中的商務用 Skype。
  
> [!IMPORTANT]
> 您是否準備好設定商務用 Skype 中的新式驗證？ 若要啟用此功能的步驟是對[以下](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。 
  
|拓撲名稱  <br/> |範例  <br/> |描述  <br/> |支援  <br/> |
|:-----|:-----|:-----|:-----|
|僅限雲端  <br/> |![支援 MA 拓樸，僅限雲端 SFB。](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)位於使用者/信箱位於： 線上  <br/> |EXO 和 SFBO 位於 MA。  <br/> 因此，授權伺服器是 Azure AD。  <br/> |多重要素驗證 (MFA)，用戶端憑證型驗證 (CBA)，條件式存取 (CA) / 行動應用程式管理 (MAM) 使用 Intune。 \*  <br/> |
|內部部署僅限  <br/> |![支援的 SFB 有 MA 拓樸，僅限內部。](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)位於使用者/信箱位於： 內部部署  <br/> |MA 是 SFB 內部部署。  <br/> 因此，授權伺服器為 ADFS。  <br/> 設定的詳細資訊，請參閱[這篇文章。](https://technet.microsoft.com/library/mt710548.aspx) <br/> |MFA (Windows 桌面版-行動用戶端不支援)。 沒有 Exchange 的整合功能。  <br/><p> **我們不建議這種方法。在這裡，請參閱：**[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)<p/> |
   
> [!IMPORTANT]
> 建議的 MA 狀態是相同的整個 Skype for Business 和 Exchange （與其線上） 以減少提示的數目。 
  
混合的拓撲牽涉到 SFB 分割網域混合的組合。 以下是目前支援的混合式的拓撲：
  
|拓撲名稱  <br/> |範例  <br/> |描述  <br/> |支援  <br/> |
|:-----|:-----|:-----|:-----|
|混合式的 1  <br/> |![支援 SFB MA 拓撲中，混合 1 （EXO + SFB）。](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> 位於使用者/信箱位於： EXO 和 SFB  <br/> |MA 未啟用 SFB;沒有 SFB MA 中的功能可以使用這種拓撲。  <br/> |SFB 否 MA 功能。  <br/> |
|混合式的 2  <br/> |![支援與 S4B 混合式拓撲 2 MA、 SFBO 加上使用 NM-EXCH-UM-1ST 上-prem.MA](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> 位於使用者/信箱位於： NM-EXCH-UM-1ST 和 SFBO  <br/> |MA 僅在適用於 SFBO。 授權伺服器是 Azure AD 中 SFBO，但 NM-EXCH-UM-1ST 內部部署 AD 隸屬使用者。  <br/> |MFA，CBA，CA/MAM 使用 Intune。\*  <br/> |
|混合式的 3  <br/> |![支援與 SFB、 EXO 與 MA，加上 NM-EXCH-UM-1ST SFB MA 內部部署。](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> 位於使用者/信箱位於： EXO + SFB，或 NM-EXCH-UM-1ST + SFB  <br/> |在此拓撲提供任何 SFB MA 功能  <br/> |SFB 否 MA 功能。  <br/> |
|混合式的 4  <br/> |![支援與 SFB、 SFBO 與 MA，加上 NM-EXCH-UM-1ST SFB MA。](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> 位於使用者/信箱位於： NM-EXCH-UM-1ST + SFBO 或 NM-EXCH-UM-1ST + SFB  <br/> |MA 上為 SFBO，因此授權伺服器是 Azure AD 中 SFBO 隸屬使用者。 SFB 和 EXO 上 prem 使用者使用 AD。  <br/> |MFA，CBA，CA/MAM Intune online 僅供使用者使用。\*  <br/> |
|混合式的 5  <br/> |![支援 MA SFB、 EXO 與 MA，以及 MA，和 NM-EXCH-UM-1ST 與內部部署的 SFB SFBO。](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> 位於使用者/信箱位於： EXO + SFBO、 EXO + SFB、 NM-EXCH-UM-1ST + SFBO，或 NM-EXCH-UM-1ST + SFB  <br/> |MA 上 EXO 和 SFBO，因此授權伺服器為 Azure AD 的使用者位於 SFBO;NM-EXCH-UM-1ST 和 SFB 中的內部部署使用者使用 AD。  <br/> |MFA，CBA，CA/MAM Intune online 僅供使用者使用。\*  <br/> |
|混合式的 6  <br/> |![在混合式 6 拓撲中，新式驗證是在所有四個 possibile 位置中的理想的 situtation 談到新式驗證]。](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> 位於使用者/信箱位於： EXO + SFBO、 EXO + SFB、 NM-EXCH-UM-1ST + SFBO，或 NM-EXCH-UM-1ST + SFB  <br/> |MA 上任何位置，因此授權伺服器為所有使用者的 Azure AD。 (線上和內部部署)  <br/>  請參閱[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)的部署步驟。 <br/> |MFA CBA，CA/MAM （透過 Intune) 的所有使用者。  <br/> |
   
\*-MFA 包含 Windows Desktop、 MAC、 iOS、 Android 裝置和 Windows Phone;CBA 包含 Windows Desktop、 iOS 和 Android 裝置;CA/MAM 使用 Intune，包括 Android 和 iOS 裝置。 
  
> [!IMPORTANT]
> 它是很重要。 請注意，使用者可能會看到在某些情況下，值得注意的是其中 MA 狀態並不相同跨所有的伺服器資源的用戶端可能需要及要求，請在此情況下所有版本的混合式拓撲中的**多個提示**。

> [!IMPORTANT]
> 另請注意，，在某些情況下 （混合 1、 3 和 5 特別） [AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online)登錄機碼必須為 Windows 桌面用戶端的適當設定。
  

