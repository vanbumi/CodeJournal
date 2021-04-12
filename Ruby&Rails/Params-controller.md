# Require params on controller	

	params.require(:user).permit(:name, :email, :role_id, :password, :password_confirmation, :avatar)