# Undelegation取消委托

If a delegator decides to stop delegating to a validator, he or she can choose to undelegate their tokens from the validator. After undelegation is initiated from a currently elected validator, the tokens will be locked for 7 [epochs](https://docs.harmony.one/home/validators/definitions/epoch-transition) \(10.5 days\) before being credited to the delegator’s account balance. Note that the unlocking of the undelegated tokens only happens at the end of every epoch. Locked tokens are still slashable if the validator double signs.

For undelegating from a non-elected validator, the token will be unlocked 7 epochs after the validator was last elected. For example, if you are undelegating from a validator who was last elected 3 epochs ago, your token will be locked for 4 epochs after the undelegation starts. This leads to a convenient result that if you undelegate from a validator who is never elected before, you can have your token returned in the current epoch.

如果委托者决定停止委托给验证者，则他或她可以选择从验证者撤消其代币。 从验证者那开始撤回代币后，代币将被锁定7个epoch，然后记入委托者的帐户余额中。 请注意，撤销委托的代币只能在每个时期结束时解锁。 如果验证者使用双重签名，则锁定的代币仍然可以被罚没。

为了从未当选的验证者撤销委托，代币将在验证者最后一次参选后的7个epoch解锁。 例如，如果您要从最近选举的3个验证者中取消委托，则您的代币将在取消委托开始后被锁定4个epoch。 也给大家提供了一些便利，即如果您从从来没有被选上的验证者中撤消委托，代币在当前epoch中即可被撤回。

