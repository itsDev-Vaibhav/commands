@Override
	public boolean isValid(String value, ConstraintValidatorContext context) {
		// TODO Auto-generated method stub
		context.disableDefaultConstraintViolation();
		if (value == null || value.trim().isEmpty()) {
			context
            .buildConstraintViolationWithTemplate("Pl flag can not be null or empty")
            .addConstraintViolation();
			return false;
		} else if (!value.toUpperCase().matches("^(YES|NO)")) {
			context
            .buildConstraintViolationWithTemplate("Pl flag can only be YES/NO.")
            .addConstraintViolation();
			return false;
		}
		return true;
	}
