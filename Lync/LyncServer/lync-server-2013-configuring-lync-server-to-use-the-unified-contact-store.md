---
title: Lync Server 2013：設定 Lync Server 使用整合連絡人存放區
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
ms.openlocfilehash: f1f913b321d700337d1cb3649c2e1351971b6d7a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506250"
---
# <a name="configuring-microsoft-lync-server-2013-to-use-the-unified-contact-store"></a>設定 Microsoft Lync Server 2013 以使用整合連絡人存放區

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-07_

整合連絡人存放區可讓使用者維護單一連絡人清單，然後讓多個應用程式（包括 Microsoft Lync 2013、Microsoft Outlook 2013 及 Microsoft Outlook Web App 2013）都能使用這些連絡人。 當您為使用者啟用整合連絡人存放區時，使用者的連絡人不會儲存在 Microsoft Lync Server 2013，然後使用 SIP 通訊協定進行檢索。 相反地，他或她的連絡人會儲存在 Microsoft Exchange Server 2013 中，而且會透過 Exchange Web 服務進行檢索。

<div>


> [!NOTE]  
> 從技術角度來看，連絡人資訊會儲存在使用者的 Exchange 2013 信箱中的一對資料夾中。 連絡人本身會儲存在名為 Lync 連絡人的資料夾中，使用者對使用者來說是可見的;連絡人的中繼資料儲存在使用者無法看見的子資料夾中。



</div>

<div>

## <a name="enabling-the-unified-contact-store-for-a-user"></a>針對使用者啟用整合連絡人存放區

如果您已在 Lync Server 2013 和 Exchange 2013 之間設定伺服器對伺服器驗證，則也會啟用整合連絡人存放區的使用;不需要其他伺服器設定。 不過，要將使用者的連絡人移動至整合連絡人存放區，則需設定其他使用者帳戶。 根據預設，使用者連絡人會保留在 Lync Server，而非整合連絡人存放區中。

使用 Lync Server 使用者服務原則來管理對整合連絡人存放區的存取。 使用者伺服器原則僅有單一屬性 (UcsAllowed)；此屬性用於決定使用者的連絡人所儲存的位置。 如果使用者是由使用者服務原則所管理，且 UcsAllowed 已設定為 True ($True) 則使用者的連絡人會儲存在統一連絡人存放區中。 如果使用者是由使用者服務原則所管理，且 UcsAllowed 已設定為 False ($False) 則會將其連絡人儲存在 Lync Server 中。

當您安裝 Lync Server 2013 時，會同時安裝單一使用者服務原則 (在全域範圍內設定) 。 這個原則中的 UcsAllowed 值設定為 True，這表示，預設會將使用者連絡人儲存在「整合連絡人存放區」中， (假設已部署並設定) 。 如果您想要將所有使用者連絡人遷移至整合連絡人存放區，您不需要執行任何動作。

如果您不想將所有連絡人遷移至整合連絡人存放區，您可以將全域原則中的 UcsAllowed 屬性設定為 False，以停用所有使用者的整合連絡人存放區：

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

停用全域原則中的整合連絡人存放區後，您就可以建立個別使用者原則，以啟用整合連絡人存放區的使用;這可讓您讓某些使用者將其連絡人保留在統一連絡人存放區中，而其他使用者仍可繼續在 Lync Server 中保留其連絡人。 您可以使用類似以下的命令來建立個別使用者的使用者服務原則：

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

在您建立新原則之後，接著您必須將該原則指派給應擁有整合連絡人存放區存取權的任何使用者。您可使用類似以下的命令，將個別使用者原則指派給使用者：

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

在指派原則給 Lync Server 之後，就會開始將使用者的連絡人遷移至整合連絡人存放區。 遷移完成後，使用者將會在 Exchange 中儲存其連絡人，而不是 Lync Server。 若使用者在遷移完成時登入 Lync 2013，將會出現一個訊息方塊，而要求他或她會登入 Lync，然後重新登入，以完成此程式。 尚未被指派此個別使用者原則的使用者，將不會將其連絡人遷移至整合連絡人存放區。 這是因為這些使用者是由全域原則所管理，且已在全域原則中停用統一連絡人存放區。

您可以從 Lync Server 管理命令介面中執行 [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) Cmdlet，以確認使用者的連絡人是否已順利遷移至整合連絡人存放區：

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

如果 Test-CsUnifiedContactStore 成功，就代表使用者 sip:kenmyer@litwareinc.com 的連絡人已經移轉至整合連絡人存放區。

</div>

<div>

## <a name="rolling-back-the-unified-contact-store"></a>復原連絡人存放區

如果您需要從統一連絡人存放區中移除使用者的連絡人 (例如，如果使用者需要在 Microsoft Lync Server 2010 上 rehomed，而且無法再使用整合連絡人存放區) 必須執行兩項操作。 首先，您必須將新的使用者服務原則指派給使用者，而不是使用統一連絡人存放區中儲存連絡人的原則。  (也就是 UcsAllowed 屬性已設定為 $False 的原則。 ) 如果您不具備這類原則，您可以使用類似下列的命令建立一個原則：

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

然後您可使用如下命令來指派這個新的個別使用者原則 (NoUnifiedContactStore)：

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

上述命令會將新原則指派給使用者 Ken Myer，同時也會防止 Ken 的連絡人移轉至整合連絡人存放區。

<div>


> [!NOTE]  
> 在某些情況下，您可以單單解除指派使用者的目前使用者服務原則達到相同的整體效果。例如，假設 Ken Myer 擁有個別使用者的使用者服務原則，該原則可啟用整合連絡人存放區，但是您的全域原則禁止整合連絡人存放區的使用。在該情況下，您可以解除指派 Ken 的個別使用者服務原則。當您那樣做時，Ken 會自動受全域原則管理，因此不再有整合連絡人存放區的存取權。<BR>若要解除指派先前所指派的個別使用者原則，請使用如前所示的相同命令，但這次需將 PolicyName 參數設為 Null 值：<BR>Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null



</div>

在處理整合連絡人存放區時，須牢記「防止 Ken 的連絡人移轉至整合連絡人存放區」這個術語。 單單將新的使用者服務原則指派給 Ken 並不會將其連絡人從整合連絡人存放區移出。 當使用者登入 Lync Server 2013 時，系統會檢查使用者的使用者服務原則，以查看其連絡人是否應該保留在統一連絡人存放區中。 如果結果為肯定 (也就是說，如果 UcsAllowed 屬性設為 $True)，那些連絡人就會移轉至整合連絡人存放區 (假設那些連絡人尚未存放在整合連絡人存放區)。 如果答案是 [否]，則 Lync Server 只會忽略使用者的連絡人，並移至下一個工作。 這表示，不論 UcsAllowed 屬性值為何，Lync Server 不會自動將使用者的連絡人從統一連絡人存放區移出。

這也表示，在指派使用者新的使用者服務原則之後，您必須執行 [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) 指令程式，以便將使用者的連絡人移出 Exchange 2013 並回到 Lync Server 2013。 例如，在將新的使用者服務原則指派給 Ken Myer 之後，您就可以使用下列命令將其連絡人移出整合連絡人存放區：

    Invoke-CsUcsRollback -Identity "Ken Myer"

果您變更使用者服務原則，但是未執行 Invoke-CsUcsRollback Cmdlet，Ken 的連絡人就不會從整合連絡人存放區移除。 如果您執行 Invoke-CsUcsRollback，但未變更 Ken Myer 的使用者服務原則，會有什麼結果呢？ 在這種情況下，Ken 的連絡人會暫時從整合連絡人存放區中遭移除。 您務必牢記此移除作業為暫時性的。 當 Ken 的連絡人從統一連絡人存放區中移除之後，Lync Server 2013 將會等候7天，然後查看已指派給 Ken 的使用者服務原則。 如果指派給 Ken 的原則仍然可啟用整合來連絡人存放區，其連絡人就會自動移回連絡人存放區。 若要將連絡人從整合連絡人存放區永久移除，除了執行 Invoke-CsUcsRollback Cmdlet 之外，您還必須變更使用者服務原。

由於大量可影響遷移的變數，因此很難估計帳戶完全遷移至整合連絡人存放區之前所需的時間。 不過，作為一般規則，遷移不會立即生效：即使遷移少量的連絡人，移動作業完成後，可能需要10分鐘或更多時間。

</div>

</div>

<span> </span>

</div>

</div>

</div>

