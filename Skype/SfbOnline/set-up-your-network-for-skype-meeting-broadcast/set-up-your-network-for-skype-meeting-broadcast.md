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
f1keywords: None
ms.custom:
- SMB
description: 瞭解商務用 Skype Online 的 Skype 會議廣播功能，可讓您安排、產生及廣播會議或事件給最多10000出席者的大型線上使用者。
ms.openlocfilehash: 95ad00be416a53e6e861ce4e9f235bded8e8075a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40990978"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>為您的 Skype 會議廣播設定網路

在您[啟用 Skype 會議廣播](enable-skype-meeting-broadcast.md)Skype 會議廣播之後，您必須設定您的網路。 如果您想要為企業外部的人員舉行網路研討會和其他廣播，請執行此步驟。

如果您不熟悉如何設定防火牆，請考慮聘用[Microsoft 合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089)來為您執行此步驟。

若要略過此步驟，而改為將其他公司新增到您的同盟，以便邀請他們進行廣播，請依照[允許使用者聯繫外部商務用 Skype 使用者](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)的步驟操作。

## <a name="step-1-set-up-allowed-domains"></a>步驟1：設定允許的網域

使用下列**其中一**種方法來設定 [允許的網域]：

## #

 **方法1：使用系統管理中心**

1. 移至系統管理中心，然後在左導覽中，按一下 [**設定** > **服務&amp;增益集**]，然後選擇 [**商務用 Skype**]。

2. 在 [**外部共用**] 頁面上的 [**網域例外**] 底下，選取 [**除了] 以外的所有網域**，然後輸入下列網域，並以逗號（，）分隔：

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. 按一下 [**儲存**]。

## #

 **方法2：使用 Windows PowerShell**

- 從 [**開始] 功能表**，以滑鼠右鍵按一下 [ **Windows PowerShell** ]，然後按一下 [**以系統管理員身分執行**]。 在 [ **Windows PowerShell** ] 視窗中，輸入每一行，然後按 enter 鍵。

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>步驟2：新增 Skype 會議廣播網域、Url 和 IP 位址

安裝程式中的第二個步驟是您首先要新增所需的網域，然後新增 Skype 會議廣播所需的 IP 位址和 Url 才能正常運作。

- [在這裡](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)**查看需要的商務用 Skype Online 端點 url 和 IP 位址**。

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>在混合式部署與組織中設定 Skype 會議廣播

如果您有商務用 Skype Online 組織和內部部署的 Lync Server 2010、Microsoft Lync Server 2013 及商務用 Skype Server 2015，且使用者都在線上和內部部署中，您將需要執行其他設定步驟您可以在上述方案中加入，以讓您的內部部署組織與商務用 Skype Online 進行通訊，並允許您所有的使用者加入 Skype 會議廣播。 若要查看這些需求，請參閱[設定 Skype 會議廣播的內部部署部署](https://go.microsoft.com/fwlink/?LinkId=617070)。

## <a name="related-topics"></a>相關主題

[啟用 Skype 會議廣播](enable-skype-meeting-broadcast.md)

[Office 365 URL 與 IP 位址範圍](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[設定商務用 Skype Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



