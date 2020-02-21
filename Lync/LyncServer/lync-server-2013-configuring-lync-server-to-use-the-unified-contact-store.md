---
title: Lync Server 2013： 設定 Lync Server 以使用整合連絡人存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use the unified contact store
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49733680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9875cb075f29f9f2efcb9328d1ac2d39d2f8ae89
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-the-unified-contact-store"></a>設定 Microsoft Lync Server 2013 使用整合連絡人存放區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-02-07_

整合連絡人存放區可讓使用者維護單一連絡人清單，然後中的多個應用程式，包括 Microsoft Lync 2013、 Microsoft Outlook 2013 和 Microsoft Outlook Web App 2013https 的那些連絡人。 當您啟用使用者的整合連絡人存放區時該使用者的連絡人不會儲存在 Microsoft Lync Server 2013，然後使用 SIP 通訊協定來擷取。 相反地，他/她的連絡人會儲存在 Microsoft Exchange Server 2013，並使用 Exchange Web 服務擷取。

<div>


> [!NOTE]  
> 技術上而言，連絡人資訊會儲存在一組使用者的 Exchange 2013 信箱中找到的資料夾。 他們自己的連絡人會儲存在名為才會顯示給使用者; Lync 連絡人資料夾連絡人的相關的中繼資料儲存至使用者看不到的子資料夾中。



</div>

<div>

## <a name="enabling-the-unified-contact-store-for-a-user"></a>針對使用者啟用整合連絡人存放區

如果您已設定 Lync Server 2013 和 Exchange 2013 之間的伺服器對伺服器驗證再也啟用整合連絡人存放區; 使用不不需要任何其他伺服器設定。 不過，要將使用者的連絡人移動至整合連絡人存放區，則需設定其他使用者帳戶。 根據預設，使用者的連絡人會保留在 Lync Server，而不是以整合連絡人存放區。

使用 Lync Server 使用者服務原則被管理至整合連絡人存放區的存取。 使用者伺服器原則僅有單一屬性 (UcsAllowed)；此屬性用於決定使用者的連絡人所儲存的位置。 如果使用者由了 UcsAllowed 已設定為 True ($True) user services 原則來管理使用者的連絡人會儲存在整合連絡人存放區中。 如果使用者由使用者服務的原則其中了 UcsAllowed 已設定為 False ($False) 然後他或她的連絡人會儲存在 Lync Server。

當您安裝 Lync Server 2013 單一 user services 原則 （設定在全域範圍） 會一併安裝。 在此原則中的了 UcsAllowed 值設為 True，意義，根據預設，使用者的連絡人會儲存在整合連絡人存放區 （假設這已部署且設定）。 如果您想要將所有使用者連絡人移轉至整合連絡人存放區您沒有完全執行任何動作。

如果您希望不要將所有的連絡人移轉至整合連絡人存放區您可以設定了 UcsAllowed 屬性設為 False 的全域原則中停用所有使用者的整合連絡人存放區：

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

您已停用整合連絡人存放區中的全域原則之後，您可以再建立啟用整合連絡人存放區; 使用個別使用者原則這可讓您有一些在整合連絡人存放區中保留其連絡人，而其他使用者會繼續保留在 Lync Server 中的其連絡人的使用者。 您可以使用類似以下的命令來建立個別使用者的使用者服務原則：

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

在您建立新原則之後，接著您必須將該原則指派給應擁有整合連絡人存放區存取權的任何使用者。您可使用類似以下的命令，將個別使用者原則指派給使用者：

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

指派原則之後 Lync Server 會開始將使用者的連絡人移轉至整合連絡人存放區。 移轉完畢之後，使用者會再有他/她連絡人會儲存在 Exchange 中，而不是 Lync Server。 如果使用者的情況登入 Lync 2013 在時間移轉完成會出現一個訊息方塊，他或她會要求您 Lync 請登出，然後再重新登入才能完成此程序。 未指派個別使用者原則的使用者將不會有其連絡人移轉至整合連絡人存放區。 這是因為這些使用者由全域原則，並已停用使用整合連絡人存放區中的全域原則。

您可以驗證該使用者的連絡人已成功移轉至整合連絡人存放區執行[Test-csunifiedcontactstore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) cmdlet 從 Lync Server 管理命令介面內：

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

如果 Test-CsUnifiedContactStore 成功，就代表使用者 sip:kenmyer@litwareinc.com 的連絡人已經移轉至整合連絡人存放區。

</div>

<div>

## <a name="rolling-back-the-unified-contact-store"></a>復原連絡人存放區

如果您需要 （例如，如果使用者需要重新隸屬於 Microsoft Lync Server 2010，即無法再使用整合連絡人存放區），從整合連絡人存放區中移除使用者的連絡人，您必須執行下列兩件事。 首先，您必須對使用者指派新的使用者服務原則，其中會禁止將連絡人儲存在整合連絡人存放區。 （也就是原則其中了 UcsAllowed 屬性已設定為 $False。）如果您不需要此類原則您可以建立一個使用類似如下的命令：

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

然後您可使用如下命令來指派這個新的個別使用者原則 (NoUnifiedContactStore)：

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

上述命令會將新原則指派給使用者 Ken Myer，同時也會防止 Ken 的連絡人移轉至整合連絡人存放區。

<div>


> [!NOTE]  
> 在某些情況下，您可以單單解除指派使用者的目前使用者服務原則達到相同的整體效果。例如，假設 Ken Myer 擁有個別使用者的使用者服務原則，該原則可啟用整合連絡人存放區，但是您的全域原則禁止整合連絡人存放區的使用。在該情況下，您可以解除指派 Ken 的個別使用者服務原則。當您那樣做時，Ken 會自動受全域原則管理，因此不再有整合連絡人存放區的存取權。<BR>若要解除指派先前所指派的個別使用者原則，請使用如前所示的相同命令，但這次需將 PolicyName 參數設為 Null 值：<BR>Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null



</div>

在處理整合連絡人存放區時，須牢記「防止 Ken 的連絡人移轉至整合連絡人存放區」這個術語。 單單將新的使用者服務原則指派給 Ken 並不會將其連絡人從整合連絡人存放區移出。 當使用者登入 Lync Server 2013 時，系統會檢查以查看他/她的連絡人是否應保留在整合連絡人存放區中的使用者的使用者服務原則。 如果結果為肯定 (也就是說，如果 UcsAllowed 屬性設為 $True)，那些連絡人就會移轉至整合連絡人存放區 (假設那些連絡人尚未存放在整合連絡人存放區)。 如果答案為否，然後 Lync Server 只會忽略使用者的連絡人，並會移到其下一個工作。 這表示，Lync Server 不會自動將使用者的連絡人從整合連絡人存放區，不論了 UcsAllowed 屬性的值。

這也表示之後將使用者指派新的 user services 原則，, 您必須執行[Invoke-csucsrollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) cmdlet 才能移動使用者的連絡人超出 Exchange 2013，並回到 Lync Server 2013。 例如，在將新的使用者服務原則指派給 Ken Myer 之後，您就可以使用下列命令將其連絡人移出整合連絡人存放區：

    Invoke-CsUcsRollback -Identity "Ken Myer"

果您變更使用者服務原則，但是未執行 Invoke-CsUcsRollback Cmdlet，Ken 的連絡人就不會從整合連絡人存放區移除。 如果您執行 Invoke-CsUcsRollback，但未變更 Ken Myer 的使用者服務原則，會有什麼結果呢？ 在這種情況下，Ken 的連絡人會暫時從整合連絡人存放區中遭移除。 您務必牢記此移除作業為暫時性的。 已從整合連絡人存放區中移除 Ken 的連絡人後，Lync Server 2013 會等候 7 天，然後再查看哪些使用者服務原則已指派給 Ken。 如果指派給 Ken 的原則仍然可啟用整合來連絡人存放區，其連絡人就會自動移回連絡人存放區。 若要將連絡人從整合連絡人存放區永久移除，除了執行 Invoke-CsUcsRollback Cmdlet 之外，您還必須變更使用者服務原。

因為大量的變數會影響移轉中，很難估計它將需要花費多少時間才能帳戶都會完全移轉至整合連絡人存放區。 一般而言，不過，移轉不會不會立即生效： 即使當移轉數目更少的連絡人可能需要 10 分鐘或更久之前移動作業就會完成。

</div>

</div>

<span> </span>

</div>

</div>

</div>

