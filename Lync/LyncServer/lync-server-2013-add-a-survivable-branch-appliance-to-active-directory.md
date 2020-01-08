---
title: Lync Server 2013：將 Survivable Branch Appliance 新增到 Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dc057318a0d241a28b8529802ea9f2016a1f5b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a>在 Lync Server 2013 中將 Survivable Branch Appliance 新增到 Active Directory

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-23_

如果您打算部署 Survivable 分支裝置，您必須將 Survivable 分支裝置新增至 Active Directory 網域服務。 在中央網站執行此程式。

<div>


> [!IMPORTANT]  
> 只有在部署 Survivable 分支裝置時，才會執行此程式。 如果您要部署 Survivable 分支伺服器，請勿執行此動作。



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a>將 Survivable 分支裝置新增至 Active Directory 網域服務

1.  以企業系統管理員群組的成員身分登入成員伺服器。

2.  按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **Active Directory 使用者和電腦**]。

3.  在 [**動作**] 功能表上，按一下 [**新增**]，然後按一下 [**電腦**]。

4.  在 [**新物件-電腦**] 對話方塊中，輸入 Survivable 分支裝置電腦物件的名稱（例如，BranchOffice1），然後按一下 [**變更**]。

5.  在 [**選取使用者或群組**] 對話方塊中，新增 [RTCUniversalSBATechnicians] 群組，然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > 分支網站上的 [RTCUniversalSBATechnicians] 群組成員稍後會將此裝置新增至網域。

    
    </div>

6.  按一下 **[確定]** 以儲存 Survivable 分支裝置電腦物件。

7.  按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **ADSI 編輯**]。

8.  在 [ **ADSI 編輯**] 中，以滑鼠右鍵按一下您在先前步驟中建立的電腦物件，然後按一下 [**屬性**]。

9.  在屬性清單中，按一下 [ **servicePrincipalName**]，然後按一下 [**編輯**]。

10. 在 [**要新增的值**] 欄位中，\<輸入 HOST\> / \<SBA Fqdn\> ，其中 SBA FQDN 是您 Survivable 分支裝置的完整功能變數名稱（FQDN）。 例如，輸入**HOST/BranchOffice1**。

11. 按一下 **[確定]** 儲存**servicePrincipalName**屬性設定，然後按一下 **[確定]** 儲存電腦物件的屬性。

12. 在**Active Directory 使用者和電腦**中，以滑鼠右鍵按一下 [**使用者**]，按一下 [**新增**]，然後按一下 [**使用者**]。

13. 在嚮導中輸入資訊，為 Survivable 分支裝置技術人員建立網域使用者帳戶。

14. 在**Active Directory 使用者和電腦**中，按一下 [**使用者**]，以滑鼠右鍵按一下使用者物件，然後按一下 [**新增至群組**]。

15. 在 **[輸入要選取的物件名稱**] 中，輸入**RTCUniversalSBATechnicians**，然後按一下 **[確定]**。

16. 針對每個分支網站技術人員，重複執行步驟12-15。

**後續步驟**：[在 Lync Server 2013 中新增分支網站至您的拓撲](lync-server-2013-add-branch-sites-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

