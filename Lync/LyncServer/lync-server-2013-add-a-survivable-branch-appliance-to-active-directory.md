---
title: Lync Server 2013： 新增至 Active Directory Survivable Branch Appliance
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fca31c97e0d059cda9f6b39a0e17e8350a37cf52
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a>將 Survivable Branch Appliance 新增至 Lync Server 2013 中的 Active Directory

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-23_

如果您計劃要部署 Survivable Branch Appliance，您必須將 Survivable Branch Appliance 新增至 Active Directory 網域服務。 請在中央網站執行這項程序。

<div>


> [!IMPORTANT]  
> 只有當您要部署 Survivable Branch Appliance，請執行此程序。 請勿執行它如果您要部署 Survivable Branch 伺服器。



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a>若要將 Survivable Branch Appliance 新增至 Active Directory 網域服務

1.  以 Enterprise Admins 群組成員的身分，登入成員伺服器。

2.  依序按一下 **[開始]**、**[系統管理工具]** 和 **[Active Directory 使用者和電腦]**。

3.  在 **[執行]** 功能表上，依序按一下 **[新增]** 和 **[電腦]**。

4.  在 [**新增物件-電腦**] 對話方塊中，輸入 Survivable Branch Appliance 的電腦物件 (例如 BranchOffice1) 的名稱，然後按一下 [**變更]**。

5.  在 **[選取使用者或群組]** 對話方塊中，新增 RTCUniversalSBATechnicians 群組，然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > 稍後會由分支網站的 RTCUniversalSBATechnicians 群組成員將此裝置新增至網域。

    
    </div>

6.  按一下 **[確定]** 儲存 Survivable Branch Appliance 的電腦物件。

7.  依序按一下 **[開始]**、**[系統管理工具]** 和 **[ADSI 編輯器]**。

8.  在 **[ADSI 編輯器]** 中，用滑鼠右鍵按一下您於先前步驟建立的電腦物件，然後按一下 **[內容]**。

9.  在屬性清單中，依序按一下 **[servicePrincipalName]** 和 **[編輯]**。

10. **若要新增的值**] 欄位中輸入主機 /\<SBA FQDN\>其中\<SBA FQDN\>是您 Survivable Branch Appliance 的完整的網域名稱 (FQDN)。 例如，輸入 **HOST/BranchOffice1.contoso.com**。

11. 按一下 **[確定]** 儲存 **servicePrincipalName** 屬性設定，然後按一下 **[確定]** 儲存電腦物件內容。

12. 在 **[Active Directory 使用者和電腦]** 中，用滑鼠右鍵按一下 **[使用者]**、按一下 **[新增]**，然後按一下 **[使用者]**。

13. 若要為 Survivable Branch Appliance 技術人員建立網域使用者帳戶精靈中輸入資訊。

14. 在 **[Active Directory 使用者和電腦]** 中，按一下 **[使用者]**、用滑鼠右鍵按一下使用者物件，然後按一下 **[加入群組中]**。

15. 在 **[輸入物件名稱來選取]** 中，輸入 **RTCUniversalSBATechnicians**，然後按一下 **[確定]**。

16. 針對每個分支網站技術人員，重複步驟 12-15。

**下一步**：[將分支網站新增至您在 Lync Server 2013 中的拓撲](lync-server-2013-add-branch-sites-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

