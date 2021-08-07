---
title: 為您的 Skype 會議廣播設定網路
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: 瞭解 Skype Online 的 商務用 Skype 會議廣播功能，此功能可讓您排程、製作會議或活動，以及將會議或活動廣播給最多 10，000 名出席者的大型線上觀眾。
ms.openlocfilehash: e5248ca2f8b8bb8080eae5eebe44e3d7c5bc01f5
ms.sourcegitcommit: f3c2559a89e1c4b3514e102cf94c38a697b4bc57
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/04/2021
ms.locfileid: "53725356"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>為您的 Skype 會議廣播設定網路

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

啟用會議[Skype廣播](enable-skype-meeting-broadcast.md)Skype會議廣播之後，您需要設定您的網路。 如果您想要為公司外部人員舉辦網路研討會和其他廣播，請執行此步驟。

> [!IMPORTANT]
> 商務用 SkypeOnline 將于 2021 年 7 月 31 日停用，此時將結束服務存取權。 我們鼓勵客戶開始升級至 Microsoft Teams 中通訊和團隊合作的核心用戶端 Microsoft 365。

如果您沒有防火牆的組組經驗，請考慮雇用 [Microsoft 合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089) 來執行此步驟。

若要略過此步驟，改為將另一個企業新增到您的聯盟，以便邀請他們加入廣播，請遵循允許使用者與外部使用者商務用 Skype[中的步驟](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)。

## <a name="step-1-set-up-allowed-domains"></a>步驟 1：設定允許的網域

使用 **下列** 其中一種方法來設定允許的網域：

### <a name="method-1-use-the-admin-center"></a>方法 1：使用系統管理中心

1. 請前往系統管理中心，然後在左側導航區中，設定  >  **[服務 &amp; 設定，** 然後選擇 [商務用 Skype。 

2. 在外部 **共用** 頁面上的網域例外情形下，選取 所有網域都受到封鎖，然後輸入下列網域，以逗號分隔 (，) ：

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. 按一下 [儲存]。

### <a name="method-2-use-windows-powershell"></a>方法 2：使用Windows PowerShell

- 在 [**開始功能表上**， 以滑鼠右鍵按一下 **Windows PowerShell** 然後按一下 **[以系統管理員的執行**> 。 在 **Windows PowerShell視窗中**，輸入每一行，然後按 Enter。

  ```PowerShell
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```PowerShell
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```PowerShell
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```PowerShell
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```PowerShell
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```PowerShell
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>步驟 2：新增Skype廣播網域、URL 和 IP 位址

設定程式的第二個步驟是先新增所需的網域，然後新增讓會議廣播Skype所需的 IP 位址和 URL。

- **在這裡查看商務用 Skype** Web 端點 URL 和 IP 位址，以新增所需的 [連線端點 URL 和 IP 位址](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)。

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>在混合式Skype組織中設定會議廣播

如果您有 商務用 Skype Online 組織，以及 Lync Server 2010、Microsoft Lync Server 2013 和 商務用 Skype Server 2015 內部部署，而且有線上和內部部署的使用者，除了上述設定步驟之外，您還需要執行其他設定步驟，讓內部部署組織能夠與 商務用 Skype Online 通訊，並允許所有使用者加入 Skype 會議廣播。 若要瞭解這些要求是什麼，請參閱為會議廣播設定Skype[部署](../../SfbServer/deploy/configure-skype-meeting-broadcast.md)。

## <a name="related-topics"></a>相關主題

[啟用 Skype 會議廣播](enable-skype-meeting-broadcast.md)

[Office 365 URL 與 IP 位址範圍](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[設定商務用 Skype Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
