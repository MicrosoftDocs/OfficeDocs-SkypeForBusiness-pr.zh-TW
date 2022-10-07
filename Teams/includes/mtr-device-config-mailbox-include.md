
您可以自訂資源帳戶回復和處理會議邀請的方式，來改善Teams 會議室會議體驗。 使用 Exchange Online PowerShell，您可以設定下列資源帳戶屬性：

- **AutomateProcessing： `AutoAccept`** 會議召集人會直接收到會議室保留決定，而不需要人為介入。

- **AddOrganizerToSubject： `$false`** 會議召集人不會新增至會議邀請的主旨。

- **DeleteComments： `$false`** 在內送會議邀請的郵件內文中保留任何文字。 這需要處理外部 Teams 和協力廠商會議，以提供 One Touch Join 體驗。

- **DeleteSubject： `$false`** 保留內送會議邀請的主旨。

- **ProcessExternalMeetingMessages： `$true`** 指定是否要處理來自 Exchange 組織外部的會議邀請。 外部 Teams 會議和第 [三方會議是必要的](/microsoftteams/rooms/third-party-join)。

- **RemovePrivateProperty： `$false`** 確保會議召集人傳送至原始會議邀請中的私人標幟維持指定。

- **AddAdditionalResponse： `$true`** AdditionalResponse 參數所指定的文字會新增至會議邀請。

- **AdditionalResponse：「這是 Microsoft Teams 會議室！」** 要新增至會議接受回復的其他文字。

若要設定這些屬性，您必須連線至 Exchange Online PowerShell。 如需詳細資訊，請參閱[連線至Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true)。

連線到 Exchange Online PowerShell 之後，您可以使用[Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing) Cmdlet 來設定資源帳戶上的信箱屬性。

下列範例會設定資源帳戶的 `ConferenceRoom01` 屬性：

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

